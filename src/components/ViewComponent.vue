<template>
  <div class="container__main">
    <div class="container__product">
      <product-info :product="selectedProduct"></product-info>
    </div>
    <div class="container__products">
      <product-list :products="products" :event="getProduct"></product-list>
    </div>
  </div>
</template>

<script>

import ProductList from "./ProductList.vue"
import products from "./../config/products.js"
import ProductInfo from "./ProductInfo.vue"

import Vue from "vue";

Vue.component("product-list", ProductList);
Vue.component("product-info", ProductInfo);

export default {

  data() {
    return {
      selectedProduct: {},
      products: products
    }
  },

  methods: {
    getProduct(ev, id) {
      this.selectedProduct = this.products.filter(item => {
        return item.id === id;
      })[0];


      console.log(this.selectedProduct)
    }
  }

}
</script>

<style scoped>
  .container__main {
    width: 935px;
    margin: 0 auto;
  }
</style>
