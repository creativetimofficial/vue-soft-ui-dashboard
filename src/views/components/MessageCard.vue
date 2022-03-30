<template>
  <div class="mt-4 card move-on-hover">
    <div class="card-body">
      <div class="d-flex">
        <p class="my-auto">{{ title }}</p>
        <div class="ms-auto">
          <div class="avatar-group">
            <a
              v-for="({ route, tooltip, image }, index) of messages"
              :key="index"
              :href="route"
              class="border-0 avatar avatar-sm rounded-circle"
              data-bs-toggle="tooltip"
              data-bs-placement="top"
              :title="tooltip"
            >
              <img
                :alt="
                  typeof image === 'string' ? 'Image placeholder' : image.alt
                "
                :src="typeof image === 'string' ? image : image.url"
              />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MessageCard",
  props: {
    title: {
      type: String,
      default: "Messages",
    },
    messages: {
      type: Array,
      route: String,
      tooltip: String,
      image: {
        type: [String, Object],
        url: String,
        alt: String,
      },
      default: () => [],
    },
  },
};
</script>
