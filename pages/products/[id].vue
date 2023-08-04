<template>
  <div>
    <Head>
      <Title>Nuxt Dojo | {{ product.title }}</Title>
      <Meta name="description" :content="product.description" />
    </Head>
    <ProductDetails :product="product" />
  </div>
</template>

<script setup>
const { id } = useRoute().params;
const uri = `https://dummyjson.com/products/${id}`;

//fetch the product
const { data } = await useFetch(uri, { key: id });
const product = data._rawValue;

if (!product) {
  throw createError({
    statusCode: 404,
    statusMessage: "Product not found",
    fatal: true,
  });
}
definePageMeta({
  layout: "products",
});
</script>

<style scoped></style>
