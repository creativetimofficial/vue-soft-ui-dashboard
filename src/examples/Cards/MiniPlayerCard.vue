<template>
  <div
    class="card card-background move-on-hover align-items-start"
    :class="`card-background-mask-${color}`"
  >
    <div class="cursor-pointer">
      <div
        class="full-background"
        style="
          background-image: url('../../../assets/img/curved-images/curved1.jpg');
        "
      ></div>
      <div class="card-body">
        <h5 class="mb-0 text-white">{{ song.title }}</h5>
        <p class="text-sm text-white">{{ song.singer }}</p>
        <div class="mt-5 d-flex">
          <button
            class="p-2 mb-0 btn btn-outline-white rounded-circle"
            type="button"
            data-bs-toggle="tooltip"
            data-bs-placement="top"
            title="Prev"
          >
            <i class="p-2 fas fa-backward"></i>
          </button>
          <button
            class="p-2 mx-2 mb-0 btn btn-outline-white rounded-circle"
            type="button"
            data-bs-toggle="tooltip"
            data-bs-placement="top"
            title="Pause"
          >
            <i class="p-2 fas fa-play"></i>
          </button>
          <button
            class="p-2 mb-0 btn btn-outline-white rounded-circle"
            type="button"
            data-bs-toggle="tooltip"
            data-bs-placement="top"
            title="Next"
          >
            <i class="p-2 fas fa-forward"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PlayerCard",
  props: {
    color: {
      type: String,
      default: "success",
    },
    song: {
      type: Object,
      default: () => ({
        title: "Some Kind Of Blues",
        singer: "Deftones",
      }),
      title: String,
      singer: String,
    },
  },
};
</script>
