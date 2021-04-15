<template>
  <h1>{{ msg }}</h1>
  <div>{{ readersNumber }} {{ book.title }}</div>

  <!-- <button @click="state.count++">count is: {{ state.count }}</button> -->
</template>

<script>
import {
  defineProps,
  reactive,
  ref,
  onMounted,
  onUpdated,
  onUnmounted,
  getCurrentInstance,
} from "vue";

export default {
  props: {
    name: {
      type: String,
      default: "name",
    },
  },
  setup(props, context) {
    console.log("props", props.name);

    const internalInstance = getCurrentInstance();
    // console.log(internalInstance);

    const readersNumber = ref(0);
    const book = reactive({ title: "Vue 3 Guide" });

    onMounted(() => {
      console.log("mounted!");
    });
    onUpdated(() => {
      console.log("updated!");
    });
    onUnmounted(() => {
      console.log("unmounted!");
    });

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
