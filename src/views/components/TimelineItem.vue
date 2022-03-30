<template>
  <div class="mb-3 timeline-block" :class="darkMode">
    <span class="timeline-step" :class="darkMode ? 'bg-dark' : ''">
      <i class="ni text-gradient" :class="`ni-${icon} text-${color}`"></i>
    </span>
    <div class="timeline-content">
      <h6
        class="mb-0 text-sm font-weight-bold"
        :class="darkMode ? 'text-white' : 'text-dark'"
      >
        {{ title }}
      </h6>
      <p class="mt-1 mb-0 text-xs text-secondary font-weight-bold">
        {{ dateTime }}
      </p>
      <p v-if="description" class="mt-3 mb-2 text-sm">
        {{ description }}
      </p>
      <span
        v-for="(badge, index) of badges"
        :key="index"
        class="badge badge-sm me-1"
        :class="`bg-gradient-${color}`"
      >
        {{ badge }}
      </span>
    </div>
  </div>
</template>
<script>
export default {
  name: "TimelineItem",
  props: {
    color: {
      type: String,
      default: "",
    },
    icon: {
      type: String,
      default: "",
    },
    title: {
      type: String,
      default: "",
    },
    dateTime: {
      type: String,
      default: "",
    },
    description: {
      type: String,
      default: "",
    },
    badges: {
      type: Array,
      default: () => [],
    },
    darkMode: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
