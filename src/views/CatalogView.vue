<script setup>
import Product from "@/components/Catalog/Product.vue";
import {ref} from "vue";
import axios from "axios";

const products = ref([])
axios.get('products')
    .then((response) => products.value = response.data)

</script>

<template>
  <div class="catalog-container">
    <section class="catalog-filter">
      <div class="filter-container">
        <div class="name-filter">Bouquet size</div>
        <ul>
          <li><label><input type="checkbox"> Large</label></li>
          <li><label><input type="checkbox"> Medium</label></li>
          <li><label><input type="checkbox"> Small</label></li>
        </ul>
      </div>
      <div class="filter-container">
        <div class="name-filter">Flowers</div>
        <ul>
          <li><label><input type="checkbox"> Roses</label></li>
          <li><label><input type="checkbox"> Lilies</label></li>
          <li><label><input type="checkbox"> Chrysanthemums</label></li>
          <li><label><input type="checkbox"> Other type</label></li>
        </ul>
      </div>
      <div class="filter-container">
        <div class="name-filter">Bouquet wrapper</div>
        <ul>
          <li><label><input type="checkbox"> Wrapping paper</label></li>
          <li><label><input type="checkbox"> Mesh</label></li>
          <li><label><input type="checkbox"> Wrapping film</label></li>
        </ul>
      </div>
    </section>

    <section class="row list-products">
      <div class="product-column" v-for="product in products">
        <Product :product="product" />
      </div>
    </section>
  </div>
</template>

<style scoped>
  .catalog-container {
    display: flex;
  }

  .catalog-container .catalog-filter {
    min-width: 200px;
    background-color: #fff;
    padding: 15px;

    border: none;
    border-radius: 8px;
  }

  .catalog-container .catalog-filter .name-filter {
    font-size: large;
    font-family: Arial, Helvetica, sans-serif;
    color: darkslategrey;
    padding-top: 10px;
    padding-bottom: 10px;
  }

  .catalog-container .list-products {
    margin-left: 15px;
  }

  .filter-container {
    margin-bottom: 15px;
    border-bottom: 1px solid #eee;
  }

  .filter-container ul {
    list-style: none;
    padding-left: 0;
    margin-top: 5px;
  }
</style>
