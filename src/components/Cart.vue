
<template>
    <div class="cart">
        <h2>Carret</h2>

        <p>Total d'articles: {{ cart.length }}</p>

        <ul>
            <li v-for="item in cart" :key="item.id">
                {{ item.name }} - {{ item.price }}€

                <button @click="eliminarProducte(item.id)">
                    🗑️
                </button>
            </li>
        </ul>

        <p class="total"> {{ total }}€</p>

        <button @click="buidarCarret" v-if="cart.length > 0">
            🗑️ Buida carret
        </button>
    </div>
</template>

<script setup>
import { inject, computed } from 'vue';

const cart = inject('cart')

const total = computed(() =>
    cart.reduce((sum, p) => sum + p.price, 0)
)

const eliminarProducte = (id) => {
    const index = cart.findIndex(item => item.id === id)
    if (index !== -1) {
        cart.splice(index, 1)
    }
}

const buidarCarret = () => {
    cart.splice(0, cart.length)
}
</script>
