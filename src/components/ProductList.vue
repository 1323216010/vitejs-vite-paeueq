<script setup>
import { ref } from 'vue'

const products = ref([
  { id: 1, name: 'Laptop', description: 'High performance laptop for professionals', price: 999.99, image: '/assets/laptop.jpg' },
  { id: 2, name: 'Smartphone', description: 'Latest model with advanced features', price: 499.99, image: '/assets/smartphone.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
  { id: 3, name: 'Tablet', description: 'Portable and powerful tablet', price: 299.99, image: '/assets/tablet.jpg' },
])

function formatPrice(price) {
  return `$${price.toFixed(2)}`;
}
</script>

<template>
  <div class="product-list">
    <h1>商品列表</h1>
    <div class="products">
      <div class="product-card" v-for="product in products" :key="product.id">
        <!-- 注意这里直接使用绝对路径 -->
        <img :src="product.image" :alt="product.name" class="product-image" />
        <h2>{{ product.name }}</h2>
        <p>{{ product.description }}</p>
        <p class="price">价格: {{ formatPrice(product.price) }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.product-list {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.products {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.product-card {
  width: 300px;
  margin: 15px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 8px;
  text-align: center;
}

.product-image {
  width: 100%;
  height: auto;
  border-radius: 4px;
}

.price {
  font-size: 18px;
  color: green;
}
</style>
