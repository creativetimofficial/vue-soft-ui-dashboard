<template>
  <div class="form-group">
    <label :for="exampleFormControlTextarea1">
      <slot />
    </label>
    <textarea
      class="form-control"
      rows="5"
      :placeholder="placeholder"
      :id="exampleFormControlTextarea1"
    ></textarea>
  </div>
</template>

<script>
export default {
  name: "vsud-textarea",
  props: {
    id: String,
    placeholder: String,
  },
};
</script>