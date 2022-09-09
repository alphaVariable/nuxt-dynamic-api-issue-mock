<script setup lang="ts">
import { ref } from 'vue';
const route = useRoute();

const slug = ref(String(route.params.slug));
console.log(slug.value);
const apicall = `https://swapi.dev/api/people/${slug.value}`;
const { data: article } = await useFetch(
  `https://swapi.dev/api/people/${slug.value}`
);
</script>
<template>
  <div>
    <NuxtLink to="/">Back to Home</NuxtLink>
    <pre>
      {{ `https://swapi.dev/api/people/${slug}` }}
      {{ route.params.slug }}
      {{ article }}
    </pre>
  </div>
</template>
