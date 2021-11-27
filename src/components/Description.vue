<template>
  <!--main-->
      <div class="container">   
        <div class="row">
          <div class="col-lg-8">
              <h1>Aca va el carrusel</h1>
          </div>
          <div class="col-lg-4">
            <br><br>
            <span> {{anuncios.TituloAnuncio}} </span>
            <em>{{anuncios.precio}}</em> <br> <br>
            <button type="button" class="btn btn-primary" style="background-color: #7FB174; color: black;">Comprar</button>
            <div class="d-flex justify-content-around" style="border: 3px solid #7FB174; padding-top: 2%; margin-top:10px;"><p><span> Vendedor: {{anuncios.Vendedor}} </span> <span> Teléfono: {{anuncios.Telefono}}</span></p></div>
          </div>
        </div>
        <div class="row">
           <div class="col">
             <h1 class="text-center">Descripción</h1>
            <div class="container-fluid">
              <div class="card-container d-flex flex-wrap justify-content-around align-items-center">
                <div class="card" style="width: 18rem; border: 3px solid #7FB174; max-width: 500px; max-height: 500px;">

                </div>
                <div class="card" style="width: 18rem; border: 3px solid #7FB174; max-width: 500px; max-height: 500px;">
                  <div class="card-body">
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Suscipit, ab perspiciatis. Quam assumenda libero necessitatibus culpa voluptates, 
                      sint ipsum </p>
                  </div>
                </div>
              </div>
            </div>
           </div>
        </div>
      </div>
    <!--/main-->
</template>

<script>
import { db } from '../db'

    export default {
      name: 'Description',
      data(){
        return{
          idAnuncio:"",
          anuncio:{},
        }
      },
      created(){
        this.idAnuncio=this.$route.params.id;
        this.traerAnuncio();  
      },
      methods:{
        traerAnuncio(){
          let this2=this;
          this.anuncio=db.collection('anuncios').doc(this.idAnuncio).get().then(function(dato){
            this2.anuncio=dato.data();
          })
        }
      }
    }
</script>

<style scoped>

</style>