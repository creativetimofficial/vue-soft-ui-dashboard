<template>
  <div>
    <navbar
      :min-nav="navbarMinimize"
      :toggle="toggleConfigurator"
      :class="isNavFixed ? navbarFixed : ''"
    />
  </div>
  <div
    class="mx-3 mt-3 border-radius-xl position-relative"
    :style="{
      backgroundImage: 'url(' + require('@/assets/img/vr-bg.jpg') + ')',
      backgroundSize: 'cover',
    }"
  >
    <sidenav
      :custom_class="mcolor"
      :class="isTransparent"
      class="fixed-start"
    />
    <main class="mt-1 main-content border-radius-lg">
      <div
        class="section min-vh-85 position-relative transform-scale-0 transform-scale-md-7"
      >
        <div class="container-fluid">
          <div class="pt-10 row">
            <div class="pt-5 text-center col-lg-1 col-md-1 pt-lg-0 ms-lg-5">
              <a
                href="javascript:;"
                class="border-0 avatar avatar-md d-block"
                data-bs-toggle="tooltip"
                data-bs-placement="left"
                title="My Profile"
              >
                <img
                  class="border-radius-lg"
                  alt="Image placeholder"
                  src="@/assets/img/team-1.jpg"
                />
              </a>
              <button
                class="p-2 mt-2 btn btn-white border-radius-lg d-block"
                type="button"
                data-bs-toggle="tooltip"
                data-bs-placement="left"
                title="Home"
              >
                <i class="p-2 fas fa-home"></i>
              </button>
              <button
                class="p-2 btn btn-white border-radius-lg d-block"
                type="button"
                data-bs-toggle="tooltip"
                data-bs-placement="left"
                title="Search"
              >
                <i class="p-2 fas fa-search"></i>
              </button>
              <button
                class="p-2 btn btn-white border-radius-lg d-block"
                type="button"
                data-bs-toggle="tooltip"
                data-bs-placement="left"
                title="Minimize"
              >
                <i class="p-2 fas fa-ellipsis-h"></i>
              </button>
            </div>
            <div class="col-lg-8 col-md-11">
              <div class="d-flex">
                <div class="me-auto">
                  <h1 class="mb-0 display-1 font-weight-bold mt-n4">28°C</h1>
                  <h6 class="mb-0 text-uppercase ms-1">Cloudy</h6>
                </div>
                <div class="ms-auto">
                  <img
                    class="w-50 float-end mt-lg-n4"
                    src="@/assets/img/small-logos/icon-sun-cloud.png"
                    alt="image sun"
                  />
                </div>
              </div>
              <div class="mt-4 row">
                <div class="col-lg-4 col-md-4">
                  <calendar-card
                    :items="[
                      {
                        time: '08:00',
                        description: `Synk up with Mark<small class='text-secondary font-weight-normal'>Hangouts</small>`,
                      },
                      {
                        time: '09:30',
                        description: `Gym<br /><small class='text-secondary font-weight-normal'>World Class</small>`,
                      },
                      {
                        time: '11:00',
                        description: `Design Review<br /><small class='text-secondary font-weight-normal'>Zoom</small>`,
                      },
                    ]"
                  />
                </div>
                <div class="mt-4 col-lg-4 col-md-4 mt-sm-0">
                  <todo-card :todos="['Shopping', 'Meeting']" />
                  <email-card />
                </div>
                <div class="mt-4 col-lg-4 col-md-4 mt-sm-0">
                  <mini-player-card />
                  <message-card
                    :messages="[
                      {
                        route: '/',
                        tooltip: '2 New Messages',
                        image: { url: image1, alt: 'Image Placeholder' },
                      },
                      {
                        route: '/',
                        tooltip: '1 New Messages',
                        image: { url: image2, alt: 'Image Placeholder' },
                      },
                      {
                        route: '/',
                        tooltip: '13 New Messages',
                        image: { url: image3, alt: 'Image Placeholder' },
                      },
                      {
                        route: '/',
                        tooltip: '7 New Messages',
                        image: { url: image4, alt: 'Image Placeholder' },
                      },
                    ]"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
  <app-footer class="py-3 bg-white border-radius-lg" />
</template>

<script>
import Sidenav from "@/examples/Sidenav";
import AppFooter from "@/examples/Footer.vue";
import Navbar from "@/examples/Navbars/Navbar.vue";
import CalendarCard from "./components/CalendarCard.vue";
import EmailCard from "./components/EmailCard.vue";
import TodoCard from "./components/TodoCard.vue";
import MiniPlayerCard from "@/examples/Cards/MiniPlayerCard.vue";
import MessageCard from "./components/MessageCard.vue";
import setTooltip from "@/assets/js/tooltip.js";

import image1 from "@/assets/img/team-1.jpg";
import image2 from "@/assets/img/team-2.jpg";
import image3 from "@/assets/img/team-3.jpg";
import image4 from "@/assets/img/team-4.jpg";

const body = document.getElementsByTagName("body")[0];

import { mapMutations, mapState } from "vuex";

export default {
  name: "VrInfo",
  components: {
    AppFooter,
    Sidenav,
    Navbar,
    CalendarCard,
    EmailCard,
    TodoCard,
    MiniPlayerCard,
    MessageCard,
  },
  data() {
    return {
      image1,
      image2,
      image3,
      image4,
    };
  },
  computed: {
    ...mapState(["isTransparent", "isNavFixed", "navbarFixed", "mcolor"]),
  },
  mounted() {
    setTooltip(this.$store.state.bootstrap);
  },
  beforeMount() {
    this.$store.state.showNavbar = false;
    this.$store.state.showSidenav = false;
    this.$store.state.showFooter = false;
    body.classList.add("virtual-reality");
    this.$store.state.isTransparent = "bg-white";
  },
  beforeUnmount() {
    this.$store.state.showNavbar = true;
    this.$store.state.showSidenav = true;
    this.$store.state.showFooter = true;
    body.classList.remove("virtual-reality");

    if (this.$store.state.isPinned === false) {
      const sidenav_show = document.querySelector(".g-sidenav-show");
      sidenav_show.classList.remove("g-sidenav-hidden");
      sidenav_show.classList.add("g-sidenav-pinned");
      this.$store.state.isPinned = true;
    }
    this.$store.state.isTransparent = "bg-transparent";
  },
  methods: {
    ...mapMutations(["navbarMinimize", "toggleConfigurator"]),
  },
};
</script>
