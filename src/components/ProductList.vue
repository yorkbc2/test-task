<template>
  <div>
    <h2 class="product__list_header">
      you may also like
    </h2>

    <div class="product__list">


      <template v-for="pr in products">
        <product-item
          :image="pr.image"
          :price="parseFloat(pr.price)"
          :oldprice="pr.oldprice"
          :sale="pr.sale"
          :id="pr.id"
          :event="event"
          :hidden="pr.hidden"
          :stars="pr.stars">

        </product-item>
      </template>

    </div>
  </div>

</template>

<script>
  import Vue from "vue";
  import Product from "./Product.vue";

  Vue.component("product-item", Product);

  export default {
    props: ['products', 'event']
  }
</script>

<style scoped>
  .product__list_header {
    text-transform: uppercase;
    letter-spacing: 1.7px;
    text-align: left;
    font-family: "Open Sans", sans-serif;
  font-weight: bolder;
    margin-left: 10px;
  }

  .product__list {
    display: -webkit-flex;
    display: -moz-flex;
    display: -ms-flex;
    display: -o-flex;
    display: flex;

    flex-direction: row;
    -webkit-flex-wrap: wrap;
    -moz-flex-wrap: wrap;
    -ms-flex-wrap: wrap;
    -o-flex-wrap: wrap;
    flex-wrap: wrap;

    position: relative;
  }

</style>
