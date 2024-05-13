<script setup lang="ts">
import { RouterView } from 'vue-router'
import { ref, reactive, computed } from 'vue'

interface AppInfo {
  name: string
  description: string
}

const count = ref(0)

const nextCount = computed(() => {
  if (count.value !== null) {
    return count.value + 1
  }
  return null
})

const appInfo: AppInfo = reactive({
  name: 'Counter',
  description: 'An app you can count on - made with vue + ts'
})

function addCount(num: number) {
  if (count.value !== null) count.value += num
}
</script>

<template>
  <header>
    <div class="wrapper">
      <h1>{{ appInfo.name }}</h1>
      <h2>{{ appInfo.description }}</h2>
    </div>
    <p>{{ count }}</p>
    <button @click="addCount">Add count</button>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}
</style>
