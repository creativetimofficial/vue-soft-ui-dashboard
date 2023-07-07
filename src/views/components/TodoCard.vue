<script setup>
import { computed } from "vue";

const getLength = computed(() => {
  return props.todos.length;
});
const props = defineProps({
  todos: {
    type: Array,
    default: () => [],
  },
});
</script>
<template>
  <div class="card bg-gradient-dark move-on-hover">
    <div class="card-body">
      <div class="d-flex">
        <h5 class="mb-0 text-white">To Do</h5>
        <div class="ms-auto">
          <h1 class="mb-0 text-white text-end mt-n2">{{ getLength }}</h1>
          <p class="mb-0 text-sm text-white">items</p>
        </div>
      </div>
      <p
        v-for="(todo, index) of props.todos"
        :key="index"
        class="mb-0 text-white"
      >
        {{ todo }}
      </p>
    </div>
    <a
      href="javascript:;"
      class="py-1 text-center w-100"
      data-bs-toggle="tooltip"
      data-bs-placement="top"
      title="Show More"
    >
      <i class="text-white fas fa-chevron-down"></i>
    </a>
  </div>
</template>
