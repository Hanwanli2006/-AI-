<template>
  <section class="card-section">
    <div class="card" v-for="card in cards" :key="card.title">
      <h2>{{ card.icon }} {{ card.title }}</h2>
      <p>{{ card.desc }}</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import { cards } from '../data/cards'
</script>

<style scoped>
.card-section {
  display: flex;
  gap: 20px;
  margin-bottom: 30px;
}

.card {
  flex: 1;
  background: white;
  padding: 20px;
  border-radius: 16px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}
</style>