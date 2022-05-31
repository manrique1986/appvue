<template>
  <div id="app">
    <NavBar />

    <h3 class="titulo1">Cerveza Artesanal</h3>
    <br />
    <MiCard
      v-for="(product, i) in products"
      :key="i"
      :id="product.id"
      :titulo="product.titulo"
      :precio="product.precio"
      :sabor="product.sabor"
      :imagen="product.imagen"
      :cantidad="product.quantity"
      :products="products"
      @add-to-cart="updateCart"
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
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932402/honey_knvkxz.jpg",
        },

        {
          id: 2,
          titulo: "Blonde",
          sabor: "Amarga",
          precio: 400,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932534/blonde2_ts180x.jpg",
        },

        {
          id: 3,
          titulo: "Ipa",
          sabor: "Amarga",
          precio: 400,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932553/ipa_yf51hn.jpg",
        },

        {
          id: 4,
          titulo: "Scottish",
          sabor: "Dulce",
          precio: 350,
          imagen:
            "https://res.cloudinary.com/dytpump6i/image/upload/v1653932564/scottish_izjelm.jpg",
        },
      ],

    productosEnCarrito: [],
    };
  },

     methods: {
        updateCart(id) {
            let result = this.products.find((prod) => {
                return prod.id == id;
            });
            this.productosEnCarrito.push(result);
        },
    },
};
</script>

<style>
.titulo1 {
  text-align: center;
  color: brown;
}


</style>
