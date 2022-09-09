<script setup lang="ts">
import { ref } from 'vue';
const router = useRouter();

const slug = ref(route.params.slug);

const { data: article } = await useFetch(
  `https://swapi.dev/api/people/${slug}`
).then((res) => {
  console.log(slug + 'fetched');
  return res.data;
});
</script>
<template>
  <div>
    <NuxtLink to="/">Back to Home</NuxtLink>
    <pre>
      {{ article }}
    </pre
  </div>
</template>
