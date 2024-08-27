<template>

  <h1 class="text-center mb-5">Market</h1>
  <div class="container">
    <div class="row">
      <Card :products="products" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Card from "./Card.vue";

export default {
  components: {
    Card,
  },

  data() {
    return {
      products: [],
    };
  },

  methods: {
    async fetchProducts() {
      try {
        const response = await axios.get("http://localhost:8080/api/products");
        console.log(response.data);
        this.products = response.data;
      } catch (error) {
        console.error("Errore durante il recupero dei prodotti:", error);
      }
    },
  },

  mounted() {
    this.fetchProducts();
  },
};
</script>

<style scoped></style>
