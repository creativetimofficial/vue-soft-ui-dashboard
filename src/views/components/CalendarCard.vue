<template>
  <div class="overflow-hidden card move-on-hover">
    <div class="card-body">
      <template v-for="({ time, description }, index) of items" :key="index">
        <div class="d-flex">
          <h6 class="mb-0 me-3">{{ time }}</h6>
          <!-- eslint-disable-next-line vue/no-v-html -->
          <h6 class="mb-0" v-html="description" />
        </div>
        <hr v-if="index !== items.length - 1" class="horizontal dark" />
      </template>
    </div>
    <a
      href="javascript:;"
      class="py-1 text-center bg-gray-100 w-100"
      data-bs-toggle="tooltip"
      data-bs-placement="top"
      title="Show More"
    >
      <i class="fas fa-chevron-down text-primary"></i>
    </a>
  </div>
</template>

<script>
export default {
  name: "CalendarCard",
  props: {
    items: {
      type: Array,
      default: () => {},
      time: [String, Number],
      description: String,
    },
  },
};
</script>
