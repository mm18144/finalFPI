<template>
<div>
<div id="app">
    <navbar-component/>
   <!-- <side-bar-component class="styleSideBar"></side-bar-component> -->
    <router-view/>
  </div>
</div>

</template>

<script >
import NavbarComponent from './components/NavbarComponent.vue'
//import SideBarComponent from './components/SideBarComponent.vue'
  export default{
    components:{
      NavbarComponent,
  //    SideBarComponent
      
    },
    data: ()=>({
      drawer:true
    }),
  }
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.styleSideBar{
  margin-top: 5px;
}
</style>
