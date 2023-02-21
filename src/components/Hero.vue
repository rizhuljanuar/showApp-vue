<script setup>
  import { defineProps, defineEmits } from 'vue'

  const {isDummyJson} = defineProps(["isDummyJson"])
  const emit = defineEmits(["selectShow"])

  const emitSelectedShow = () => {
    emit("selectShow")
  }
</script>

<template>
  <div class="hero">
    <h1>{{ isDummyJson ? 'Dummy Json' : 'Ricky and Morty' }}</h1>
    <p @click="emitSelectedShow">{{ isDummyJson ? 'Ricky and Morty' : 'Dummy Json' }}</p>
  </div>
</template>

<style scoped>
  .hero {
    height : 40vh;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    flex-direction: column
  }
  .hero img {
    position: absolute;
    height: 700px;
    opacity: 0.1;
  }
  .hero h1 {
    font-size: 100px;
    font-weight: bold;
  }
  .hero p {
    cursor: pointer;
  }
</style>
