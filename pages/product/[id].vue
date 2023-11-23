<script lang="ts" setup>
import DetailProduct from "~/components/DetailProduct.vue";
import { products } from "~/composables/constants/products";
import { Products } from "~/types/products";

definePageMeta({
  middleware: ["user-access"],
});

const route = useRoute();
const id =
  typeof route.params.id === "string" ? parseInt(route.params.id) : null;
const product = ref(products.find((item: Products) => item.id === id));
</script>
<template>
  <DetailProduct :product="product" />
</template>
