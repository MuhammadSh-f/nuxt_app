<template>
  <div class="card text-center">
    <!-- <button
      class="material-symbols-outlined rounded"
      :onclick="() => deleteTask()">
      delete
    </button> -->
    <h2 class="font-bold text-gray-500 m-4 truncate">{{ task.name }}</h2>
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
