<script setup>
import { inject } from 'vue'
import CartItem from './CartItem.vue'
const { cart, removeFromCart } = inject('cart')
</script>
<template>
  <div class="grid flex-col flex-1 gap-4 justify-betweeen" v-auto-animate>
    <CartItem
      v-for="item in cart"
      v-bind:key="item.id"
      :title="item.title"
      :price="item.price"
      :image-url="item.imageUrl"
      @on-click-remove="() => removeFromCart(item)"
    />
  </div>
</template>
