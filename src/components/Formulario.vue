<template>
 <div class="container">
        <div class="row">
            <div class="col-lg-12 mt-3 text-center">
                <h1 style="text-transform: uppercase;">nuevo anuncio</h1>
            </div>
        </div>
        <div class="row mt-4">
            <div class="col-lg-6 ">
                <div style="border: 1px solid black;">
                  <div style="margin: 30px 25px;">
                    <p>parte1</p>
                    <b-form-group label="Estado:" v-slot="{ ariaDescribedby }">
                        <b-form-radio v-model="estado" :aria-describedby="ariaDescribedby" name="some-radios" value="nuevo">Nuevo</b-form-radio>
                        <b-form-radio v-model="estado" :aria-describedby="ariaDescribedby" name="some-radios" value="usado">Usado</b-form-radio>
                     </b-form-group>

                    <div class="row"> 
                      <b-form-group id="input-group-2" label="Marca:" label-for="input-2"  class="col" >
                          <b-form-input
                            id="input-2"
                            placeholder="Ingresa la Marca"
                            required
                            class="col"
                            v-model="Marca"
                          ></b-form-input>
                      </b-form-group>
                    </div>
                    <div class="row"> 
                      <b-form-group id="input-group-3" label="Modelo:" label-for="input-3"  class="col" >
                          <b-form-input
                            id="input-3"
                            placeholder="Ingrese el modelo"
                            required
                            class="col"
                            v-model="Modelo"
                          ></b-form-input>
                      </b-form-group>
                    </div>
                    
                    <div class="container">
                      <label for="inputPantalla">Pantalla:</label>
                      <input type="number" id="inputPantalla" v-model="pantalla">
                    </div>
                   <br>
                    <div>
                      <b-form inline>
                        <label class="mr-sm-2" for="inline-form-custom-select-pref">Sistema:</label>
                        <b-form-select
                          id="inline-form-custom-select-pref"
                          class="mb-2 mr-sm-2 mb-sm-0"
                          :options="['Android', 'Windows', 'Ios']"
                          :value="null"
                          v-model="Sistema"
                        ></b-form-select>
                      </b-form>
                    </div>
                    <br>
                    <div>
                      <label for="inputRom" >ROM:</label>
                      <input type="number" id="inputRom" v-model="Rom">
                    </div>
                    <br>
                    <div>
                      <label for="inputRam" >RAM:</label>
                      <input type="number" id="inputRam" v-model="RAM">
                    </div>                    
                  </div>
                </div>

                <div style="margin-top: 15px; border: 1px solid black; height: 175px;">
                    <div style="margin: 30px 25px;">
                      <p>Imagenes</p>
                    </div>
                </div>
            </div>
            <div class="col-lg-6" style="border: 1px solid black;">
              <p>parte 3</p>
                    <div class="row"> 
                      <b-form-group id="input-group-4" label="Titulo breve del anuncio:" label-for="input-4"  class="col" >
                          <b-form-input
                            id="input-4"
                            placeholder=""
                            required
                            class="col"
                            v-model="TituloAnuncio"
                          ></b-form-input>
                      </b-form-group>
                    </div>

                    <div class="row"> 
                      <b-form-group id="input-group-5" label="Vendedor:" label-for="input-5"  class="col" >
                          <b-form-input
                            id="input-5"
                            placeholder=""
                            required
                            class="col"
                            v-model="Vendedor"
                          ></b-form-input>
                      </b-form-group>
                    </div>  
                    <br>
                    <div>
                      <label for="inputTel" >Telefono:</label>
                      <input type="number" id="inputTel" placeholder="numero sin guion" v-model="Telefono"> 
                    </div>    
                    <br>
                    <b-row class="mt-2">
                       <b-col sm="2">
                      <label for="textarea-large">Descripción:</label>
                    </b-col>
                    <b-col sm="10">
                      <b-form-textarea
                        id="textarea-large"
                        size="lg"
                        placeholder="Descripcion del telefono"
                        v-model="Descripcion"
                      ></b-form-textarea>
                      </b-col>
                    </b-row>               
                    <br>
                    <div>
                      <label for="inputPrecio" >Precio:</label>
                      <input type="number" id="inputPrecio" v-model="precio"> 
                    </div>    
                    <br>

                    <div>
                       <b-button squared variant="success" class="mr-4">Cancelar</b-button>

                       <b-button squared variant="success" @click="crear">Crear</b-button>
                    </div> 
            </div>
        </div>
    </div>
</template>

<script>
import { db } from '../db'
    export default {
        name: 'Formulario',
        data(){
          return{
            anuncios: [],
            Descripcion: "",
            estado:"",
            Marca: "",
            Modelo: "",
            RAM: 0,
            Rom: 0,
            Telefono: 0,
            TituloAnuncio: "",
            pantalla: 0,
            precio: 0,
            Sistema: "",
            Vendedor: "",
          }
        },
        firestore:{
           anuncios: db.collection('anuncios')
        },
        methods:{
          crear(){
            var nuevo={
            Descripcion: this.Descripcion,
            estado:this.estado,
            Marca: this.Marca,
            Modelo: this.Modelo,
            RAM: this.RAM,
            Rom: this.Rom,
            Telefono: this.Telefono,
            TituloAnuncio: this.TituloAnuncio,
            pantalla: this.pantalla,
            precio: this.precio,
            Sistema: this.Sistema,
            Vendedor: this.Vendedor,
            };
            db.collection('anuncios').add(nuevo);

            this.Descripcion= "",
            this.estado="",
            this.Marca="",
            this.Modelo= "",
            this.RAM= 0,
            this.Rom= 0,
            this.Telefono= 0,
            this.TituloAnuncio= "",
            this.pantalla=0,
            this.precio= 0,
            this.Sistema="",
            this.Vendedor=""
          }
        }
    }
</script>

<style scoped>

.parte1{
  border: 1px solid black;
}

</style>