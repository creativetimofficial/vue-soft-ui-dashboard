<template>
  <div class="form-check">
    <input class="form-check-input" type="checkbox" :name="name" :id="id" :checked="checked" />
    <label :for="id" class="custom-control-label">
      <slot />
    </label>
  </div>
</template>

<script>
export default {
  name: "vsud-checkbox",
  props: {
    name: String,
    id: String,
    checked: String,
  },
};
</script>
