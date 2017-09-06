<template>
  <div class="product__price">

    <template v-if="oldprice && sale == true">
      <span class="product__price_string">
        $
      </span>
      <span class="product__price_string _old">

        {{oldprice}}

      </span>
      <span class="product__price_string _sale">

        ${{parseFloat(price).toFixed(2)}}

      </span>
    </template>

    <template v-else>
      <span class="product__price_string">

        $ {{parseFloat(price).toFixed(2)}}

      </span>
    </template>

  </div>
</template>

<script>
  export default {
    props: ["price", "sale", "oldprice"]
  }
</script>

<style scoped>
  /* color : #8ae6cf*/
  /* color-red : ca415d*/

  .product__price {
    position: absolute;

    bottom: 22px;
    right: 0;
    min-width: 63px;

    background-color: #8ae6cf;
    padding: 4px;
  }

  .product__price span {
    display: inline-block;
  }

  .product__price_string {
    font-weight: 600;
    color: #2c303d;
  }

  .product__price_string._old {
    text-decoration: line-through;
  }

  .product__price_string._sale {
    color: #ce2c52;

    margin-left: 10px;
  }


</style>

