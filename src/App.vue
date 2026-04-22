<template>
  <div class="container">
    <HeaderSection />

    <FeatureCards />

    <ChatBox />
  </div>
</template>

<script setup lang="ts">
import HeaderSection from './components/Header.vue'
import FeatureCards from './components/FeatureCards.vue'
import ChatBox from './components/ChatBox.vue'
</script>

<style scoped>
.container {
  padding: 30px;
  background: #f5f7fb;
  min-height: 100vh;
}
</style>