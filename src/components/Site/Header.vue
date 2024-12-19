<template>
  <header>
    <div class="container row between vertical-center">
      <div>
        <img class="logo" src="@/assets/img/logo1.webp">
      </div>
      <div class="search">
        <input type="text" placeholder="Search your perfect bouquet ... " v-model="searchResult" @keyup="search">
        <ul class="search-result" v-show="isShowSearch">
          <li>Товар 1</li>
          <li>Товар 2</li>
          <li>Товар 3</li>
        </ul>
      </div>

      <div>
        <img class="some-img" src="@/assets/img/flowers-img.jpg">
      </div>

      <nav>
        <ul class="row">
          <li><router-link to="/">>Home</router-link></li>
          <li><router-link to="/about">>About</router-link></li>
          <li><router-link to="/catalog">>Collection</router-link></li>
          <li><router-link to="/login">Log in</router-link></li>
          <li class="cart">
            <img src="@/assets/img/cart-bag.png">
          </li>
        </ul>
      </nav>
    </div>
  </header>

</template>

<script setup>
import {RouterLink} from "vue-router";
</script>
