<template>
  <div class="container">
      <div class="row">
          <div class="col-lg-6 ls-12 firstContainer">
              <div class=containerPrice id="orderPrice">
                  <b-form inline>
                        <div class="optionPrice">
                            <label for="inputPrice">Precio:</label>
                            <input type="number" id="inputPrice" placeholder="$" v-model="price1"> 
                        </div> 
                        <div>
                            <label for="inputTill" >hasta:</label>
                            <input type="number" id="inputTill" placeholder="$" v-model="price2 "> 
                        </div> 
                         <b-button type="reset" variant="success" class="buttonFilter" @click="rangoPrecio">Filtrar</b-button>
                  </b-form>    
                </div>
          </div>
          <div class="col-lg-6 ls-12 secondContainer">
            <div>
                <div class="containerPrice" id="containerOrder">
                    <span>Ordenar por:</span>
                    <b-button type="submit" variant="success" class="buttonPrice"  @click="filtrarPorPrecio"><b-icon icon="arrow-up"></b-icon>Precio</b-button>
                    <b-button type="reset" variant="success" class="buttonDate" v-model="date1" @click="filtrarPorFecha"><b-icon icon="calendar3"></b-icon> Fecha</b-button>
                </div>
            </div>
          </div>
      </div>
  </div>
</template>

<script>
import { bus } from '../main'
//import {bus} from '../main'
    export default {
        name:'FilterPrice',
        data(){
            return{
                price1:null,
                price2:null,
                date1:null
            }
        },
        methods:{
            rangoPrecio(){
                if(this.price1 || this.price2){
                    bus.$emit("buscarRango", this.price1)
                }
            },
            filtrarPorPrecio(){
                bus.$emit("buscarPorPrecio")
            },
            filtrarPorFecha(){
                if(this.date1){
                    bus.$emit("buscarPorFecha", this.date1)
                }
            }
        }
    }
</script>

<style>
.containerPrice{
    border: 1px solid green;
    margin-top: 10px;
    overflow: hidden;
    
}
.opcion{
    float: left;
}

.itemOption{
    float: left;
}

.buttonPrice{
    margin: 5px 7px;
}
.optionPrice{
    margin: 5px 15px;
}

#containerOrder{
    height: 95px;
}

#orderPrice{
    height: 95px;
}
.buttonFilter{
    margin: 10px 15px;
    margin-top: 28.5px;
}

</style>