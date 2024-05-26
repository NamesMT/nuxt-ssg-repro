<script setup lang="ts">
const { data } = await useLazyAsyncData('apiResult', () => new Promise(r => setTimeout(r, 0)).then(() => `Hello! - ${Date.now()}`), { default: () => 'Loading...' as const })
</script>

<template>
  <div>
    This should be SSG and not change: <span :style="{ color: 'red' }">{{ data }}</span>
  </div>
</template>
