<template>
  <ul class="pagination" :class="getClasses(color, size)">
    <slot />
  </ul>
</template>

<script>
export default {
  name: "SoftPagination",
  props: {
    color: {
      type: String,
      default: "success",
    },
    size: {
      type: String,
      default: "md",
    },
  },
  methods: {
    getClasses: (color, size) => {
      let colorValue, sizeValue;

      colorValue = color ? `pagination-${color}` : null;
      sizeValue = size ? `pagination-${size}` : null;

      return `${colorValue} ${sizeValue}`;
    },
  },
};
</script>
