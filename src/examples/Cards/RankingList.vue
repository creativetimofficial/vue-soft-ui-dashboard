<script setup>
defineProps({
  title: {
    type: String,
    default: "",
  },
  item: {
    type: Array,
    default: () => {},
    title: String,
    date: String,
    amount: String,
    icon: String,
    color: String,
  },
  horizontalBreak: {
    type: Boolean,
    default: true,
  },
});
</script>
<template>
  <h6
    v-if="title"
    class="text-uppercase text-body text-xs font-weight-bolder mb-3 pt-2"
  >
    {{ title }}
  </h6>
  <ul class="list-group">
    <li
      v-for="({ icon, title: itemTitle, date, color, amount }, index) of item"
      :key="index"
      class="pb-0 border-0 list-group-item justify-content-between ps-0 border-radius-lg"
    >
      <div class="d-flex">
        <div class="d-flex align-items-center">
          <button
            class="p-3 mb-0 btn btn-icon-only btn-rounded me-3 btn-sm d-flex align-items-center justify-content-center"
            :class="`btn-outline-${color}`"
          >
            <i class="fas" :class="icon"></i>
          </button>
          <div class="d-flex flex-column">
            <h6 class="mb-1 text-sm text-dark">{{ itemTitle }}</h6>
            <span class="text-xs">{{ date }}</span>
          </div>
        </div>
        <div
          class="text-sm d-flex align-items-center text-gradient font-weight-bold ms-auto"
          :class="`text-${color}`"
        >
          {{ amount }}
        </div>
      </div>
      <hr
        v-if="horizontalBreak && index !== item.length - 1"
        class="mt-3 mb-2 horizontal dark"
      />
      <div v-else class="mt-3 mb-2" />
    </li>
  </ul>
</template>
