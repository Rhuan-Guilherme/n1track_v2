<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

onMounted(() => {
    initFlowbite();
})
</script>

<template>
  <header>
    
  </header>

  <main>
    <RouterView />
  </main>
  

  <footer>

  </footer>
</template>

