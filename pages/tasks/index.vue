<template>
  <div>
    <h2>Tasks</h2>
    <div class="card container mx-auto p-4 flex justify-between mb-5">
      <h1>Create Task</h1>
      <input placeholder="Task Name..." id="taskName" />
      <button class="btn" @click="sendTaskRequest">Submit</button>
    </div>
    <div class="grid grid-cols-4 gap-5" id="tasks" ref="true">
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

const sendTaskRequest = async () => {
  const taskName = document.getElementById("taskName").value;
  await $fetch("https://task-manager-api-w9ye.onrender.com/api/v1/tasks", {
    method: "POST",
    body: { name: taskName },
    response: true,
  });

  // window.location.reload();
};

useHead({
  title: "Task Manager | Tasks",
  meta: [{ name: "description", content: "Nuxt 3 Merch" }],
});
</script>

<style scoped></style>
