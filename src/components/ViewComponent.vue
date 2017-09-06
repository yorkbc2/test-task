<template>
  <div class="container__main">
    <div class="container__product">

    </div>
    <div class="container__products">
      <product-list></product-list>
    </div>
  </div>
</template>

<script>

import Product from "./Product.vue"
import ProductList from "./ProductList.vue"

import Vue from "vue";

Vue.component("product-list", ProductList);
</script>

<style scoped>
  .container__main {
    width: 935px;
    margin: 0 auto;
  }
</style>
