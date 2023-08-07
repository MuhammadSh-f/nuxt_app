<template>
  <div class="card text-center">
    <h2 class="font-bold text-gray-500 m-4 truncate">{{ task.name }}</h2>
    <h3 class="font-bold text-gray-500 m-4 truncate">{{ task.completed }}</h3>
    <NuxtLink :to="`/tasks/${task._id}`">
      <p class="btn my-4">View Details</p>
    </NuxtLink>
  </div>
</template>

<script setup>
const { task } = defineProps(["task"]);
</script>

<style scoped>
.thumb {
  max-height: 120px;
  max-width: 70%;
  margin: 0 auto;
}
</style>
