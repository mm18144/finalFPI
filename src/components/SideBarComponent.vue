<template>
 <div>
    <b-button v-b-toggle.sidebar-1>Sub-menu</b-button>
    <b-sidebar id="sidebar-1" title="" bg-variant="success" shadow>
      <div class="px-3 py-2">
        <div>
          <b-form-checkbox name="check-button" switch size="lg">
          <span>Nuevo</span>
        </b-form-checkbox>
      </div>
        <div class="container">
          <span>Marca</span>
          <b-form-checkbox id="checkbox-1" v-model="mark" name="checkbox-1" value="Samsung" unchecked-value="not_accepted" @change="castFilter">
            <span>Samsung</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-2" v-model="mark" name="checkbox-2" value="Huawei" unchecked-value="not_accepted" @change="castFilter">
            <span>Huawei</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-3" v-model="mark" name="checkbox-3" value="Nokia" unchecked-value="not_accepted" @change="castFilter">
            <span>Nokia</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-4" v-model="mark" name="checkbox-4" value="Iphone" unchecked-value="not_accepted" @change="castFilter">
            <span>Iphone</span>
          </b-form-checkbox>
          
          <b-form-checkbox id="checkbox-5" v-model="mark" name="checkbox-5" value="Xiaomi" unchecked-value="not_accepted" @change="castFilter">
            <span>Xiaomi</span>
          </b-form-checkbox>
        </div>

        <div class="container">
          <span>Sistema</span>
           <b-form-checkbox id="checkbox-6" v-model="sistemas" name="checkbox-6" value="Android" unchecked-value="not_accepted" @change="castFilter">
            <span>Android</span>
           </b-form-checkbox>

           <b-form-checkbox id="checkbox-7" v-model="sistemas" name="checkbox-7" value="Windows" unchecked-value="not_accepted" @change="castFilter">
            <span>Windows</span>
           </b-form-checkbox>

           <b-form-checkbox id="checkbox-8" v-model="sistemas" name="checkbox-8" value="Ios" unchecked-value="not_accepted" @change="castFilter">
            <span>Ios</span>
           </b-form-checkbox>
        </div>

        <div class="container">
          <span>Pantalla</span>
          <b-form-checkbox id="checkbox-9" v-model="screen" name="checkbox-9" value="6.0" unchecked-value="not_accepted" @change="castFilter">
            <span>6.0</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-10" v-model="screen" name="checkbox-10" value="5.5" unchecked-value="not_accepted" @change="castFilter">
            <span>5.5</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-11" v-model="screen" name="checkbox-11" value="5" unchecked-value="not_accepted" @change="castFilter">
            <span>5</span>
          </b-form-checkbox>
        </div>
      </div>
    </b-sidebar>

    
  </div>

</template>

<script>
import {bus} from '../main'
    export default {  
        name:'SideBarComponent',
        data(){
          return{
            mark:[],
            sistemas:[],
            screen:[]
          }
        },
        methods:{
          castFilter(){
            var x={mark:[], sistemas:[], screen:[]}
            if(this.mark.length>0){
              x.mark=this.mark
            }
            if(this.sistemas.length>0){
              x.sistemas=this.sistemas
            }
            if(this.screen.length>0){
              x.screen=this.screen
            }  
            bus.$emit("changeFilter", x)
          }
        }
    }
</script>

<style scoped>
.container{
  border: 1px solid black;
  margin-top: 25px;
  padding-inline-end: 15em;
  
}

</style>