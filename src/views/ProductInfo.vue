<script setup>
import {useRoute} from "vue-router";
import axios from "axios";
import {ref} from "vue";

const id = useRoute().params.id
const product = ref({})

axios.get('products/' + id)
    .then((response) => product.value = response.data)

</script>

<template>
  <div class="container">
    <div class="row vertical-center between">
      <section class="product-card-slider">
        <img src="@/assets/img/bouquet-1.jpg">
      </section>

      <section class="product-card-info">
        <div class="cool-name">{{ product.name }}</div>

        <div>
          {{ product.info }}


<!--          This is a photo of a beautiful flower-->
<!--          bouquet arranged with soft yellow roses,-->
<!--          creamy white hydrangeas, light pink lisianthus,-->
<!--          and sprigs of greenery. The bouquet is wrapped in-->
<!--          elegant white and green paper with decorative accents,-->
<!--          giving it a fresh and sophisticated appearance. It is-->
<!--          displayed in a clear glass vase, highlighting the-->
<!--          delicate and harmonious composition of the flowers.-->
        </div>


        <div class="product-card-price-container">
          <div class="row">
            <div class="price ex-price">{{ product.exprice }} ₽</div>
            <div class="price">{{ product.price }} ₽</div>
          </div>

          <br />

          <div class="row">
            <button class="btn-cart">Buy now</button>
            <button class="btn-like">
              <img src="@/assets/img/icon-heart.png">
            </button>
            <button class="btn-like">
              <img src="@/assets/img/cart-bag.png">
            </button>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>

</style>