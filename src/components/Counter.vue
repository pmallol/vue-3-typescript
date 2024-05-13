<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'
import fetchCount from '@/services/fetchCount';

onMounted(() => {
  fetchCount((initialCount) => {
    count.value = initialCount
  })
})

const count = ref(0)

const nextCount = computed(() => {
  if (count.value !== null) {
    return count.value + 1
  }
  return null
})

function addCount(num: number) {
  if (count.value !== null) count.value += num
}
</script>

<template>
  <div>
    <p>{{ count }}</p>
    <button @click="addCount">Add count</button>
  </div>
</template>