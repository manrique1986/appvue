<template>
  <div class="productos">
    <div class="card " style="width: 18rem">
      <h5 class="card-title text-center">{{ titulo }}</h5>
      <!-- <img :src="getImgUrl()" class="card-img-top d-block w-50" :alt="titulo"> -->
      <div class="card-body">
        <p class="card-text">${{ precio }}</p>
        <button type="button" class="btn btn-warning text-center" @click="addToCart()">
          Agregar
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MiCard",
  props: {
    titulo: {
      type: String,
      required: true,
    },
    precio: {
      type: Number,
      required: true,
    },

    id: {
      type: Number,
      required: true,
    },
    sabor: {
      type: String,
      required: true,
    },

    imagen: {
      type: String,
      required: true,
    },
  },

  methods: {
    getImgUrl() {
      return require(`@/assets/${this.imagen}`);
    },
  },

   addToCart() {
            this.$emit("add-to-cart", this.id);
        },
};
</script>

<style>
.productos {
  padding: 25px;
  border-radius: 15px;
  box-shadow: 1px 4px 10px 0 brown;
  float: right;
}
</style>
