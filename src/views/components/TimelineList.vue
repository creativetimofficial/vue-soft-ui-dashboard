<template>
  <div class="card" :class="darkMode ? 'bg-gradient-dark' : ''">
    <div class="pb-0 card-header" :class="darkMode ? 'bg-transparent' : ''">
      <h6 :class="darkMode ? 'text-white' : ''">{{ title }}</h6>
      <!--  eslint-disable-next-line vue/no-v-html -->
      <p class="text-sm" v-html="description"></p>
    </div>
    <div class="p-3 card-body">
      <div
        class="timeline timeline-one-side"
        :data-timeline-axis-style="darkMode ? 'dashed' : 'dotted'"
      >
        <slot />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TimelineList",
  props: {
    title: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
    darkMode: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
