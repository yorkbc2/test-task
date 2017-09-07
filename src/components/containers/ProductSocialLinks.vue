<template>
  <div class="social__container">
    <ul class="social__list">

      <li :class="inline === true ? 'social__item _inline' : 'social__item'" v-for="item in links">

        <a :href="item.url">
          <i :class="'fa ' + item.icon"></i>
        </a>

      </li>

    </ul>
  </div>
</template>


<script>
import links from "./../../config/social.js"

  export default {
    props: ["inline"],
    data() {
      return {
        links: links
      }
    }
  }
</script>

<style scoped>
  .social__list {
    margin: 0;
    padding: 0;
  }

  .social__item {
    display: block;
    list-style: none;

    width: 40px;
    height: 38px;
    padding-top: 2px;
    font-size: 16pt;
    border: 2px solid #2c87ce;
    text-align: center;
    margin: 0 6px;
    border-radius: 50%;
  }

  .social__item a {
    color: #2c86ce;
  }

  .social__item._inline {
    display: inline-block;
    margin-bottom: 5px;
  }
</style>
