<template>
  <div>
    <b-nav tabs fill>
      <b-nav-item>Inicio</b-nav-item>
      <b-nav-item>Productos</b-nav-item>
      <b-nav-item>Contactos </b-nav-item>

      <button @click="ventana = true" class="btn btn-outline-dark">
        <i class="bi-cart-fill me-1"></i>
        Carrito
        <span
          class="badge bg-dark text-white ms-1 rounded-pill"
        ></span>
      </button>
    </b-nav>
  </div>
</template>

<script>
export default {
  name: "NavBar",

  props: {
    producto: {
      type: Array,
    },
    cart: {
      type: Array,
    }
  },
  data() {
    return {
      ventana: false,
    };
  },

   computed: {
    cartCounter () {
      return this.cart.reduce((acc, product) => acc + product.quantity, 0)
    }
  }
};
</script>

<style>
</style>
