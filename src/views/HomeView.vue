<script setup lang="ts">
import { ref } from 'vue'
import Hello from '../components/Hello.vue'

// Cambia esto a 'false' para apagarlo y ver el contenido real
const showProvisionalEffect = ref(true)
</script>

<template>
  <Hello v-if="showProvisionalEffect" />
  
  <div v-else>
    <h1>Aldair DEV | DAIR XP</h1>
  </div>
</template>
