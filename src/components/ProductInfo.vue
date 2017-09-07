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
      <div class="product__stars">
        <product-stars :count="product.stars"></product-stars>
        <product-share-it></product-share-it>
      </div>
      <div class="product__stars"></div>
      <div class="product__description_p">
        <h4>details: </h4>
        <p>
          {{product.description}}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
  import Vue from "vue";
  import PriceInfoContainer from "./containers/PriceInfoContainer.vue";
  import StarsContainer from "./containers/StarsContainer.vue";
  import ProductShareIt from "./containers/ProductShareIt.vue"

  Vue.component("product-price", PriceInfoContainer)
  Vue.component("product-stars", StarsContainer)
  Vue.component("product-share-it", ProductShareIt)

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

  .product__description_p {
    font-family: "Open Sans", sans-serif;
  }

  .product__description_p h4 {
    text-transform: uppercase;
    letter-spacing: 0.8px;
    font-weight: bolder;
  }

  .product__description_p p{
    margin: 0;
    padding: 0;
    font-size: 0.813em;
  }

  .product__item_id {
    color: #2c303d;
    font-size: 10pt;
    letter-spacing: .2px;
    opacity: 0.5;
    font-family: "Open Sans", sans-serif;
  }

  .product__image {
    flex: 2;
  }
  .product__image img {
    width: 100%;
    height: auto;
  }

  .product__description {
    margin-left: 60px;
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
