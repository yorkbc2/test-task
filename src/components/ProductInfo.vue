<template>
  <div class="product__info">
    <div class="product__image">
      <img :src="product.image" :alt="product.title">
    </div>
    <div class="product__description">
      <div class="product__title">
        <h2>
          {{product.title}}
        </h2>
        <span class="product__item_id">
          Item #: {{product.item_id}}
        </span>
      </div>
      <div class="product__price">
        <product-price :price="product.price"
          :oldprice="product.oldprice"
          :sale="product.sale"></product-price>
      </div>
    </div>
  </div>
</template>

<script>
  import Vue from "vue";
  import PriceInfoContainer from "./containers/PriceInfoContainer.vue";

  Vue.component("product-price", PriceInfoContainer)

  export default {
    props: ["product"]
  }
</script>

<style scoped>
  .product__info {
    display: -webkit-flex;
    display: -moz-flex;
    display: -ms-flex;
    display: -o-flex;
    display: flex;
    flex-direction: row;
    -webkit-flex-wrap: nowrap;
    -moz-flex-wrap: nowrap;
    -ms-flex-wrap: nowrap;
    -o-flex-wrap: nowrap;
    flex-wrap: nowrap;
    justify-content: flex-start;
  }

  .product__item_id {
    color: #2c303d;
    font-size: 10pt;
    letter-spacing: .2px;
    opacity: 0.5;
    font-family: "Open Sans", sans-serif;
  }

  .product__image {
    flex: 1;
  }
  .product__image img {
    width: 100%;
    height: auto;
  }

  .product__description {
    margin-left: 20px;
    flex: 2;
    text-align: left;
  }

  .product__title h2 {
    text-transform: uppercase;
    letter-spacing: 1.4px;
    font-size: 1.8em;
    font-weight: bolder;
    margin: 0 0 5px 0;
  }

</style>
