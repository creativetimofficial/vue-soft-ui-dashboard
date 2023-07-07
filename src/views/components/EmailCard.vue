<script setup>
defineProps({
  route: {
    type: String,
    default: "",
  },
  text: {
    type: String,
    default: "Emails (21)",
  },
  tooltip: {
    type: String,
    default: "Check your emails",
  },
});
</script>
<template>
  <div class="mt-4 card move-on-hover">
    <div class="card-body">
      <div class="d-flex">
        <p class="mb-0">{{ text }}</p>
        <a
          :href="route"
          class="ms-auto"
          target="_blank"
          data-bs-toggle="tooltip"
          data-bs-placement="top"
          :title="tooltip"
        >
          Check
        </a>
      </div>
    </div>
  </div>
</template>
