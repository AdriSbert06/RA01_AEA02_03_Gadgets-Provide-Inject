<template>
    <div class="cart">
        <h2>Carret</h2>

        <ul>
            <li v-for="item in cart" :key="item.name">{{ item.name }} - {{ item.price }}€</li>
        </ul>
        <p class="total"> {{ total }}</p>
    </div>

</template>

<script setup>
import { inject, computed } from 'vue';

const cart = inject('cart')

const total = computed(() =>
    cart.reduce((sum, p) => sum + p.price, 0)
)

</script>