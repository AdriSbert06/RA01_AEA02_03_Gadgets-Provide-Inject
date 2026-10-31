
<script setup>
defineProps({
  item: {
    type: Object,
    required: true
  }
});

const emit = defineEmits(['eliminar']);
</script>

<template>
  <li class="cart-item">
    <span>{{ item.name }}</span>

    <span>{{ item.price }}€</span>

    <button
      class="delete-btn"
      @click="emit('eliminar', item.id)"
    >
      🗑️
    </button>
  </li>
</template>
