<template >

    <div class="card" style="width: 18rem" v-for="product in products">
      <img
        :src="product.image_url"
        class="card-img-top"
        alt="Immagine prodotto"
      />
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <p class="card-text">{{ product.description }}</p>
        <!--<a href="#" class="btn btn-primary">Go somewhere</a>-->
      </div>
    </div>

</template>

<script>
export default {
   props:{
    products:{
        type:Array,
        required: true
    }
   },

  data() {
    return {};
  },
};
</script>

<style lang="scss">

</style>
