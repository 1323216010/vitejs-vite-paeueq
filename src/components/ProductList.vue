<script setup>
import { ref } from 'vue'

const products = ref([
{ id: 1, name: 'Laptop', description: 'High performance laptop for professionals', price: 999.99, image: '/assets/laptop.jpg' },
{ id: 2, name: 'Smartphone', description: 'Latest model with advanced features', price: 499.99, image: '/assets/smartphone.jpg' },
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
  width: 70%; /* 调整总体宽度使得页面比例更合适 */
  max-width: 1200px; /* 最大宽度限制，防止在大屏幕上过于扩展 */
  margin: 0 auto; /* 水平居中 */
}

.products {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 100%; /* 使用100%宽度以适应父容器的宽度 */
}

.product-card {
  width: calc(33.333% - 30px); /* 每行三个卡片，减去的30px是左右margin的总和 */
  margin: 15px; /* 维持外边距 */
  padding: 10px; /* 维持内边距 */
  border: 1px solid #ccc;
  border-radius: 8px;
  text-align: center;
  box-sizing: border-box;
}

.product-image {
  max-width: 80%;
  height: auto;
  border-radius: 4px;
  margin: auto;
}

.price {
  font-size: 18px;
  color: green;
}

/* 响应式布局的媒体查询 */
@media (max-width: 800px) {
  .product-card {
    width: calc(50% - 30px); /* 在较小屏幕上每行显示两个卡片 */
  }
}

@media (max-width: 500px) {
  .product-card {
    width: calc(100% - 30px); /* 在手机屏幕上每行显示一个卡片 */
  }
}
</style>
