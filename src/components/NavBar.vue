<template>
  <div>
 <nav class="  navbar navbar-expand-lg navbar-light bg-light">
      <div class=" BarraNav container-fluid">
        <a class="navbar-brand " href="">HALSEY</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav mx-auto">
            <li class="nav-item ">
              <to class="nav-link active" aria-current="page" to="">Inicio</to>
            </li>
        <li class="nav-item ">
              <to class="nav-link active" aria-current="page" to="">Productos</to>
            </li>
            <li class="nav-item">
            <to class="nav-link active" aria-current="page" to="">Galeria</to>
            </li>
            <li class="nav-item">
            <to class="nav-link active" aria-current="page" to="#">Contacto</to>
            </li>
          </ul>
        </div>
      </div>

       <button class="btn btn-outline-dark" type="submit" data-bs-toggle="modal" data-bs-target="#myModal">
              <i class="bi-cart-fill me-1"></i>
              Carrito
              <span id="contador" class="badge bg-dark text-white ms-1 rounded-pill"></span>
            </button>

    </nav>
  </div>
</template>

<script>
export default {
  name: "NavBar",

  props: {
    producto: {
      type: Array,
    },
  },
  data() {
    return {
      ventana: false,
    };
  },

  computed: {
    productosCounter() {
      return this.products.length;
    },
  },
};
</script>

<style>
</style>
