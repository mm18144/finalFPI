<template>
 <div>
    <b-button v-b-toggle.sidebar-1>Toggle Sidebar</b-button>
    <b-sidebar id="sidebar-1" title="Sidebar" shadow>
      <div class="px-3 py-2">
        <div>
          <b-form-checkbox v-model="checked" name="check-button" switch size="lg">
          <span>Nuevo</span>
        </b-form-checkbox>
      </div>
        <div class="container">
          <span>Marca</span>
          <b-form-checkbox id="checkbox-1" v-model="status" name="checkbox-1" value="accepted" unchecked-value="not_accepted">
            <span>Samsung</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-2" v-model="status" name="checkbox-2" value="accepted" unchecked-value="not_accepted">
            <span>Huawei</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-3" v-model="status" name="checkbox-3" value="accepted" unchecked-value="not_accepted">
            <span>Nokia</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-4" v-model="status" name="checkbox-4" value="accepted" unchecked-value="not_accepted">
            <span>Iphone</span>
          </b-form-checkbox>
          
          <b-form-checkbox id="checkbox-5" v-model="status" name="checkbox-5" value="accepted" unchecked-value="not_accepted">
            <span>Xiaomi</span>
          </b-form-checkbox>
        </div>

        <div class="container">
          <span>Sistema</span>
           <b-form-checkbox id="checkbox-6" v-model="status" name="checkbox-6" value="accepted" unchecked-value="not_accepted">
            <span>Android</span>
           </b-form-checkbox>

           <b-form-checkbox id="checkbox-7" v-model="status" name="checkbox-7" value="accepted" unchecked-value="not_accepted">
            <span>Windows</span>
           </b-form-checkbox>

           <b-form-checkbox id="checkbox-8" v-model="status" name="checkbox-8" value="accepted" unchecked-value="not_accepted">
            <span>Ios</span>
           </b-form-checkbox>
        </div>

        <div class="container">
          <span>Pantalla</span>
          <b-form-checkbox id="checkbox-9" v-model="status" name="checkbox-9" value="accepted" unchecked-value="not_accepted">
            <span>6.0</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-10" v-model="status" name="checkbox-10" value="accepted" unchecked-value="not_accepted">
            <span>5.5</span>
          </b-form-checkbox>

          <b-form-checkbox id="checkbox-10" v-model="status" name="checkbox-10" value="accepted" unchecked-value="not_accepted">
            <span>5</span>
          </b-form-checkbox>
        </div>
      </div>
    </b-sidebar>

    
  </div>

</template>

<script>
    export default {
        name:'SideBarComponent',
    }
</script>

<style scoped>
.container{
  border: 1px solid black;
  margin-top: 25px;
  padding-inline-end: 15em;

}

</style>