<script setup>
defineProps({
  color: {
    type: String,
    default: "success",
  },
  size: {
    type: String,
    default: "md",
  },
});
function getClasses(color, size) {
  let colorValue, sizeValue;

  colorValue = color ? `pagination-${color}` : null;
  sizeValue = size ? `pagination-${size}` : null;

  return `${colorValue} ${sizeValue}`;
}
</script>
<template>
  <ul class="pagination" :class="getClasses(color, size)">
    <slot />
  </ul>
</template>
