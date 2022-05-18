<template>
  <div class="form-check form-switch">
    <input
      :id="id"
      class="form-check-input"
      :class="$attrs.class"
      type="checkbox"
      :name="name"
      :checked="checked"
    />
    <label class="form-check-label" :class="labelClass" :for="id">
      <slot />
    </label>
  </div>
</template>

<script>
export default {
  name: "SoftSwitch",
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
    labelClass: {
      type: String,
      default: "",
    },
  },
};
</script>
