<template>
  <div class="product__share_container">
    <a @click="openLittleModalWindow()" href="#" class="product__share">
      Share it!
    </a>
    <div v-if="showLinks === true" class="product__share_links">
      <button @click="closeLittleModalWindow()" class="product__links_cancel">
        &times;
      </button>
      <h3 class="product__share _small">Share with</h3>
      <product-social :inline="true"></product-social>
    </div>
  </div>
</template>

<script>

import Vue from "vue"
import ProductSocialLinks from "./ProductSocialLinks.vue";

Vue.component("product-social", ProductSocialLinks)

  export default {
    props: ["inline"],

    data() {
      return {
        showLinks: false
      }
    },

    methods: {
      openLittleModalWindow() {
        this.showLinks = !this.showLinks;
      },

      closeLittleModalWindow() {
        this.showLinks = false;
      }
    }
  }
</script>

<style scoped>
  .product__share_container {
    position: relative;
    display: inline-block;
  }
  .product__share {
    text-decoration: none;
    color: #2c87ce;
    font-family: "Open Sans", sans-serif;
    font-weight: bold;
    font-size: 18pt;
    margin-left: 15px;
  }

  .product__share._small {
    font-size: 16pt
  }

  .product__share_links {

    position: absolute;

    top: 100%;
    width: 287px;
    left: -100px;
    box-shadow: 0px 0px 3px #333;
    background-color: #fff;
    padding: 10px;

    animation: topAnim 0.3s ease-in-out forwards;
  }

  @keyframes topAnim {
    from {top: 100%; opacity: 0;}
    to {top: 140%; opacity: 1;}
  }

  .product__share_links::before {
    content: "";
    position: absolute;

    width: 20px;
    height: 20px;

    transform: rotate(45deg);
    box-shadow: -2px -2px 2px #ccc;

    left: 50%;
    top: -8px;
    background-color: #fff;
  }

  .product__share_links h3 {
    margin: 4px 6px;
    margin-bottom: 8px;
  }

  .product__links_cancel {
    position: absolute;
    border: 0;
    background-color: transparent;
    color: #2c87ce;
    top: 10px;
    right: 10px;
    font-size: 26pt;

    outline: none;
    cursor: pointer;
  }
</style>
