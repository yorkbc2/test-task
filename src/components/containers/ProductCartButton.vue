<template>
  <button class="cart__button"
    :type="submit === true ? 'submit' : 'button'">
      {{label}}
    </button>
</template>

<script>
  export default {
    props: ["label", "submit"]
  }
</script>

<style scoped>
  .cart__button {
    border-radius: 500px;
    padding: 15px 56px;
    margin: 20px 0;

    font-size: 13pt;
    text-transform: uppercase;
    text-decoration: none;
    font-weight: bold;
    font-family: "Open Sans", sans-serif;

    border: 0;

    background-color: #8ae6cf;
    color: #2c303d;

    outline: none;
  }
</style>
