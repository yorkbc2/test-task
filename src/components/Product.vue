<template>
  <div class="product__item" @click="event($event, id)">

    <div class="product__image">
      <img width="265px" :src="image" :alt="'Image'">
    </div>

    <post-price
      :sale="sale"
      :price="price"
      :oldprice="oldprice"></post-price>

  </div>
</template>

<script>

  import Vue from "vue";
  import PriceContainer from "./containers/PriceContainer.vue";

  Vue.component("post-price", PriceContainer);

  export default {
    name: "Product",
    props: ["image", "price", "oldprice", "sale", "event", "id"]
  }
</script>

<style scoped>
  .product__item {
    flex-basis: 265px;
    border: 1px solid red;

    margin: 10px;
    background-color: #000;

    position: relative;

    cursor: pointer;
  }
</style>
