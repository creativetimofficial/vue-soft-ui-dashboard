<template>
  <div class="form-group">
    <label :for="id">
      <slot />
    </label>
    <textarea
      :id="id"
      class="form-control"
      rows="5"
      :placeholder="placeholder"
    ></textarea>
  </div>
</template>

<script>
export default {
  name: "SoftTextarea",
  props: {
    id: {
      type: String,
      required: true,
    },
    placeholder: {
      type: String,
      default: "Your text here...",
    },
  },
};
</script>
