<template>
  <div class="star__container">
    <template v-for="(item, index) in maxstars">
      <span v-if="item <= count" class="star__item _red">
        &#9733;
      </span>
      <span v-else class="star__item">
        &#9733;
      </span>
    </template>
  </div>
</template>

<script>

  export default {
    props: ["count"],
    data() {
      return {
        maxstars: 5
      }
    }
  }
</script>

<style scoped>
  .star__container   {
    display: inline-block;
  }

  .star__item {
    font-size: 1.7em;
    letter-spacing: -2px;
  }

  .star__item._red {
    color: #ce2c52;
  }
</style>
