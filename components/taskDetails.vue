<template>
  <div class="card">
    <div class="grid grid-cols-2 gap-10">
      <div class="p-7">
        <h2 class="text-4xl my-7">{{ task.name }}</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
const { task } = defineProps(["task"]);
</script>

<style scoped>
img {
  max-width: 400px;
}
</style>
