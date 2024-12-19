<script setup>
defineProps({
  product: {}
})

const buy = () => {
  alert('Added!')
  // send request to API
}
</script>

<template>
  <div class="product-item">
    <div class="img-container">
      <img src="@/assets/img/bouquet-1.jpg">
    </div>
    <h3>
      <router-link :to="{name: 'product-info', params: {id: product.id}}">{{ product.name }}</router-link>
    </h3>
    <div class="row vertical-center between">
      <div>
        <button class="btn-cart" @click="buy">
          Buy Now
        </button>
      </div>
      <div class="price">{{ product.price}} ₽</div>
    </div>
    <div class="hover-block"></div>
    <div class="sale" v-show="product.isSale">
      <img src="@/assets/img/icon-discount.png">
    </div>
  </div>
</template>