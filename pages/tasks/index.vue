<template>
  <div>
    <h2>Tasks</h2>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in tasks">
        <taskCard :task="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: "tasks",
});

const { data } = await useFetch(
  "https://task-manager-api-w9ye.onrender.com/api/v1/tasks"
);
const tasks = data._rawValue.tasks;

useHead({
  title: "Task Manager | Tasks",
  meta: [{ name: "description", content: "Nuxt 3 Merch" }],
});
</script>

<style scoped></style>
