<template>
  <div id="app">
    <NavBar
    />
    <br>
    <MiCard
   v-for="(product, i) in products" :key="i"
                    :id="product.id"
                    :titulo="product.titulo"
                    :precio="product.precio"
                    :sabor="product.sabor"
                    :imagen="product.imagen"
                    :cantidad="product.cantidad"
                    @add-to-cart="addToCart"
  />
  </div>
</template>

<script>
import MiCard from "./components/MiCard.vue";
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    MiCard,
    NavBar,
  },

  data() {
    return {
      products: [
        {
          id: 1,
          titulo: "Honey",
          sabor: "Dulce",
          precio: 350,
          imagen: "assets/honey.jpg"
        },

        {
          id: 2,
          titulo: "Blonde",
          sabor: "Amarga",
          precio: 400,
          imagen: "assets/blonde2.jpg"
        },

        {
          id: 3,
          titulo: "Ipa",
          sabor: "Amarga",
          precio: 400,
          imagen: "assets/ipa.jpg"
        },

        {
          id: 4,
          titulo: "Scottish",
          sabor: "Dulce",
          precio: 350,
          imagen: "assets/scottish.jpg"
        },
      ],

      productsInCart:[]
    };



  },


    // methods: {
    //     addToCart(id) {
    //         let productAdded = this.productsInCart.find((item) => {
    //             return item.id == id;
    //         });
    //         if (productAdded != null) {
    //             productAdded.cantidad++;
    //         }
    // },

}


</script>

<style>
</style>
