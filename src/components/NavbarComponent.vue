<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
        <b-navbar-brand href="#">Tienda CellPhone</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
            <b-nav-form>
                <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
            </b-nav-form>
        </b-navbar-nav>
        <div class="button-group">
            <b-button id="button-inicio">Inicio</b-button>
        </div>
        <div>
            <b-button id="button-statistics">Estadisticas</b-button>
        </div>
        <div>
            <b-button id="button-plus"><p class="h5 mb-2" id="button-agregar"><b-icon icon="plus-circle"></b-icon></p></b-button> 
        </div>

        <div>
            <b-button id="button-plus-car"><p class="h5 mb-2" id="button-car-agregar"><b-icon icon="cart-plus-fill"></b-icon></p></b-button> 
        </div>
        </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
    export default {
        name: 'NavbarComponent',


    }
</script>

<style scoped>
.button-group{
    margin-right: 2.5px;
    margin-left: 2.5px;
}
#button-inicio{

}

#button-plus{
    margin-right: 2.5px;
    margin-left: 2.5px;
}

#button-agregar{
    width: 30px;
    height: 16.5px;
}

#button-plus-car{
    margin-right: 2.5px;
    margin-left: 2.5px;
}

#button-car-agregar{
    width: 30px;
    height: 16.5px;
}

</style>