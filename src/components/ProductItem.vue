<template>
    <div class="product-item">
        <div class="product-info">
            <span class="name">{{ product.name }}</span>
            <span class="price">{{ product.price }}€</span>
        </div>
    </div>
    <button @click="addToCart">Add to cart</button>
</template>

<script setup>
import { inject, defineProps } from 'vue';

const props = defineProps(['product'])
const cart = inject('cart')

const addToCart = () =>{
    cart.push(props.product)
    alert(`${props.product.name} afegit al carret!`)
}
</script>