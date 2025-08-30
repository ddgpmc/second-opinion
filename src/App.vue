<template>
  <div id="app">
    <Header />
    <Hero />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'

export default defineComponent({
  name: 'App',
  components: { 
    Header,
    Hero 
  }
})
</script>
