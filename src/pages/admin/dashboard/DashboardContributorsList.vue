<template>
  <va-card class="d-flex dashboard-contributors-list">
    <va-card-title>
      <h1>ㅇㅇ</h1>
    </va-card-title>

    <va-card-content>
      <va-inner-loading style="width: 100%">
        <div v-for="(i, idx) in visibleList" :key="idx" class="mb-3">
          <va-progress-bar :model-value="i.value" :color="getProgressBarColor(idx)"> {{ i.value }}명</va-progress-bar>
          <p class="mt-2">{{ i.age }}대</p>
        </div>
      </va-inner-loading>
    </va-card-content>
  </va-card>
</template>

<script setup lang="ts">
  import { ref } from 'vue'

  const visibleList = ref([
    { age: 10, value: 0 },
    { age: 20, value: 20 },
    { age: 30, value: 30 },
    { age: 40, value: 3 },
    { age: 50, value: 0 },
  ])

  function getProgressBarColor(idx: number) {
    const themeColors = ['primary', 'success', 'info', 'danger', 'warning']

    if (idx < themeColors.length) {
      return themeColors[idx]
    }

    const keys = Object.keys(themeColors)
    return themeColors[keys[(keys.length * Math.random()) << 0] as unknown as number]
  }
</script>

<style scoped lang="scss">
  .dashboard-contributors-list {
    flex-direction: column;

    .inner-loading {
      height: 100%;
    }
  }
</style>
