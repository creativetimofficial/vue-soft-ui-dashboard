<script setup>
import RankingList from "./RankingList.vue";

defineProps({
  card: {
    type: Object,
    title: String,
    subtitle: String,
    date: String,
    default: () => {},
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
  <div class="card h-100">
    <div class="p-3 pb-0 card-header">
      <div class="row">
        <div class="col-md-6">
          <h6 class="mb-0">{{ card.title }}</h6>
        </div>
        <div
          v-if="card.date"
          class="col-md-6 d-flex justify-content-end align-items-center"
        >
          <i class="far fa-calendar-alt me-2"></i>
          <small>{{ card.date }}</small>
        </div>
      </div>
    </div>
    <div class="p-3 card-body">
      <ranking-list
        :title="card.subtitle"
        :item="item"
        :horizontal-break="horizontalBreak"
      />
      <slot />
    </div>
  </div>
</template>
