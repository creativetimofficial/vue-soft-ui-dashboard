<script setup>
import { computed } from "vue";
import { useStore } from "vuex";

const store = useStore();
const isRTL = computed(() => store.state.isRTL);

defineProps({
  to: {
    type: [Object, String],
    required: true,
  },
  navText: {
    type: String,
    required: true,
  },
});
</script>
<template>
  <router-link class="nav-link" :to="to" v-bind="$attrs">
    <div
      class="text-center bg-white shadow icon icon-shape icon-sm border-radius-md d-flex align-items-center justify-content-center"
      :class="isRTL ? ' ms-2' : 'me-2'"
    >
      <slot name="icon"></slot>
    </div>
    <span class="nav-link-text" :class="isRTL ? ' me-1' : 'ms-1'">{{
      navText
    }}</span>
  </router-link>
</template>
