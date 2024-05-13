<script setup lang="ts">
import { reactive } from 'vue'
import Counter from './components/Counter.vue'

interface AppInfo {
  name: string
  description: string
}


const appInfo: AppInfo = reactive({
  name: 'Counter',
  description: 'An app you can count on - made with vue + ts'
})


</script>

<template>
  <header>
    <div class="wrapper">
      <h1>{{ appInfo.name }}</h1>
      <h2>{{ appInfo.description }}</h2>
    </div>
  </header>

  <Counter></Counter>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}
</style>
