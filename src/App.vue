<script setup lang="ts">
import BitcoinQuote from './components/BitcoinQuote.vue'
import { ref, onMounted } from 'vue'

let responseData = ref(null);

onMounted(() => {
  axios.get('https://api.coindesk.com/v1/bpi/currentprice.json').then((response) => {
    responseData.value = response.data;
  }).catch((error) => {
    console.error(error);
  }) 
}) 
</script>

<template>
  <div>
    <img src="./assets/Bitcoin.svg.png" class="logo" alt="Vite logo" />
  </div>
  <BitcoinQuote :responseView="responseData" v-if="responseData" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 1em #ffd45daa);
}
</style>
