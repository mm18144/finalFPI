<template>
    <div class="container-fluid">
        <side-bar-component/> 
        <filter-price/>
        <div class="card-container d-flex flex-wrap justify-content-around align-items-center">
            <b-card
                v-for="(anuncio,key) in anuncios" :key="key"    
                img-src="https://picsum.photos/600/300/?image=25"
                img-alt="Image"
                img-top
                tag="article"
                style="max-width: 20rem;"
                class="mb-2 mt-3"
                id="cardStyle"
            >
                <b-card-text>
                <h4><span>$</span>{{anuncio.precio}}</h4>
                <h6>{{anuncio.TituloAnuncio}}</h6>
                <span>{{anuncio.id}}</span>
                </b-card-text>

                <b-button href="#" variant="primary">Go somewhere</b-button>
            </b-card>            
        </div>
    </div>
</template>

<script>
import FilterPrice from '../components/FilterPrice.vue'
import SideBarComponent from '../components/SideBarComponent.vue'
import { db } from '../db'
import {bus} from '../main'
    export default {
        name: 'Tarjetas',
        data(){
            return{
                anuncios:[],
                originalAd:[]
            }
        },
        firestore:{
            anuncios: db.collection('anuncios')
        },
        components:{
            SideBarComponent, FilterPrice,
        },
        methods:{
            filterAds(filtros){
                this.limpiar()
                if(filtros==null){
                    return
                }    
                if(filtros.mark==null || filtros.sistemas==null || filtros.screen==null){
                    return
                }    
                this.anuncios=this.anuncios.filter((item)=>{
                    if(filtros.sistemas.length==0 && filtros.screen.length==0 && filtros.mark.length==0)
                        return true

                     //verificando marca
                    if(filtros.mark.length>0){
                        for(var y=0; y<filtros.mark.length; y++){
                            if(item.Marca==filtros.mark[y])
                            return true
                        }
                    }      

                    //verificacion de SO
                    if(filtros.sistemas.length>0){
                        for(var x=0; x<filtros.sistemas.length; x++){
                            if(item.Sistema==filtros.sistemas[x])
                            return true
                        }
                    }
  
                    //verificando pantalla
                    if(filtros.screen.length>0){
                        for(var j=0; j<filtros.screen.length; j++){
                            if(item.pantalla==filtros.screen[j])
                            return true
                        }
                    }                                       
                    return false     
                })        
            
            },
            limpiar(){
                if(this.originalAd.length>0){
                    this.anuncios=this.originalAd.slice()
                }
            },
            filterString(cadena){
                this.limpiar()
                this.anuncios=this.anuncios.filter((item)=>{
                    var x=item.TituloAnuncio.toLowerCase().indexOf(cadena.toLowerCase())
                    return (x>=0)
                })
            }

        },
        mounted(){
            this.originalAd=this.anuncios.slice()

            bus.$on("changeFilter", (data)=>{
                console.log(data)
                this.filterAds(data)
            })

            bus.$on("searchString", (data)=>{
                console.log(data)
                this.filterString(data)
            })
        },    

        
    }
</script>

<style scoped>
#cardStyle{
    width: 300px;
    height: 400px;
    max-width: 300px;
    max-height: 400px;
}

</style>