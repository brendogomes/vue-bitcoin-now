<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{ responseView }>()
</script>

<template>
  <section id="section-container">
    <div v-for="quote in props.responseView.bpi" class="card">
      <p v-html="quote.symbol"></p>
      <div>
        <h2>{{ quote.rate }}</h2>
      </div>
    </div>
  </section>

  <small>{{ props.responseView.disclaimer }}</small>
</template>

<style scoped>
#section-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

#section-container .card {
  background-color: #383838;
  border-radius: 12px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 26px;
}

.card:nth-child(2) {
  margin: 0 10px;
  margin-bottom: 26px;
}

h2 {
  margin: 0 0 0 10px;
}

p {
  font-size: 2em;
  font-weight: 500;
  text-align: left;
  margin: 0;
}
</style>
