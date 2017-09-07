<template>
  <div class="product__price">

    <template v-if="oldprice && sale == true">
      <h3 class="product__price_string _old">

        ${{parseFloat(oldprice).toFixed(2)}}

      </h3>
      <h3 class="product__price_string _sale">

        ${{parseFloat(price).toFixed(2)}}

      </h3>
    </template>

    <template v-else>
      <h3 class="product__price_string">

        $ {{parseFloat(price).toFixed(2)}}

      </h3>
    </template>

  </div>
</template>

<script>
  export default {
    props: ["price", "sale", "oldprice"]
  }
</script>

<style scoped>

  h3 {
    font-size: 1.5em;
    display: inline-block;
    text-transform: uppercase;
    font-family: "Open Sans", sans-serif;
    font-weight: bolder;
  }

  .product__price_string {
    color :#000;
    font-family: 24pt;
    line-height: 7.36pt;
  }

  .product__price_string._sale {
    margin-left: 20px;
    color: #ce2c52;
  }

  .product__price_string._old {
    text-decoration: line-through;
  }

</style>
