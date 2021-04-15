<template>
  <h1>{{ msg }}</h1>
  <div>{{ readersNumber }} {{ book.title }}</div>

  <!-- <button @click="state.count++">count is: {{ state.count }}</button> -->
</template>

<script>
import { defineProps, reactive, ref } from "vue";

export default {
  setup() {
    const readersNumber = ref(0);
    const book = reactive({ title: "Vue 3 Guide" });

    // expose to template
    return {
      readersNumber,
      book,
    };
  },
};
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
