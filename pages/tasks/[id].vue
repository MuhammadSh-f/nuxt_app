<template>
  <div>
    <Head>
      <Title>Task Manager | {{ task.title }}</Title>
    </Head>
    <taskDetails :task="task" />
  </div>
</template>

<script setup>
const { id } = useRoute().params;
const uri = `https://task-manager-api-w9ye.onrender.com/api/v1/tasks/${id}`;

//fetch the task
const { data } = await useFetch(uri, { key: id });
const task = data._rawValue.task;

if (!task) {
  throw createError({
    statusCode: 404,
    statusMessage: "task not found",
    fatal: true,
  });
}
definePageMeta({
  layout: "tasks",
});
</script>

<style scoped></style>
