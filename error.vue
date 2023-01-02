<template>
  <NuxtLayout>
    <div>
      <h1>Error</h1>
      <p>Something went wrong</p>
      <p>
        <strong>{{ error.message }}</strong>
      </p>
      <div v-if="error.statusCode == '404'">
        <h1>404 - page does not exist</h1>
      </div>
    </div>
    <p>
      Go to the
      <a class="hover:cursor-pointer" @click="handleError">first lesson</a>
    </p>
  </NuxtLayout>
</template>

<script setup>
const error = useError();
const handleError = () => {
  clearError({
    redirect:
      "/course/chapter/1-chapter-1/lesson/1-introduction-to-typescript-with-vue-js-3",
  });
};
</script>
