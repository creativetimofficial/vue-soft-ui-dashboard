<template>
  <div class="form-check">
    <input
      :id="id"
      class="form-check-input"
      type="radio"
      :name="name"
      :checked="checked"
    />
    <label class="custom-control-label" :for="id">
      <slot />
    </label>
  </div>
</template>

<script>
export default {
  name: "SoftRadio",
  props: {
    name: {
      type: String,
      required: true,
    },
    id: {
      type: String,
      required: true,
    },
    checked: {
      type: Boolean,
      default: false,
    },
  },
};
</script>
