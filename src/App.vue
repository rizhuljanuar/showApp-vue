<script setup>
  import {ref} from 'vue'
  import RickMortyCards from './components/RickMortyCards.vue'
  import Hero from './components/Hero.vue'
  import DummyJsonCardsSuspense from './components/DummyJsonCardsSuspense.vue'

  const isDummyJson = ref(true)
</script>

<template>
  <main>
    <Hero 
      :isDummyJson="isDummyJson"
      @selectShow="isDummyJson = !isDummyJson"
    />

    <KeepAlive>
      <Component :is="isDummyJson ? DummyJsonCardsSuspense : RickMortyCards" />
    </KeepAlive>
  </main>
</template>

<style scoped>

</style>
