<template>
  <div>
    <h2>Products</h2>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in data.tasks">
        <ProductCard :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
definePageMeta({
  layout: "products",
});

const { data } = useFetch(
  "https://task-manager-api-w9ye.onrender.com/api/v1/tasks"
);
console.log(data);

useHead({
  title: "Nuxt Dojo | Merch",
  meta: [{ name: "description", content: "Nuxt 3 Merch" }],
});
</script>

<style scoped></style>
