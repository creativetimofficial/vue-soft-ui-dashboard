<script setup>
import { onBeforeMount, computed } from "vue";
import { useStore } from "vuex";

import Sidenav from "./examples/Sidenav";
import Configurator from "@/examples/Configurator.vue";
import Navbar from "@/examples/Navbars/Navbar.vue";
import AppFooter from "@/examples/Footer.vue";

const store = useStore();
const isNavFixed = computed(() => store.state.isNavFixed);
const isAbsolute = computed(() => store.state.isAbsolute);

const navClasses = computed(() => {
  return {
    "position-sticky blur shadow-blur mt-4 left-auto top-1 z-index-sticky":
      isNavFixed.value,
    "position-absolute px-4 mx-0 w-100 z-index-2": isAbsolute.value,
    "px-0 mx-4 mt-4": !isAbsolute.value,
  };
});

// mutations
const toggleConfigurator = () => store.commit("toggleConfigurator");
const navbarMinimize = () => store.commit("navbarMinimize");

onBeforeMount(() => {
  store.state.isTransparent = "bg-transparent";
});
</script>
<template>
  <sidenav
    :custom_class="store.state.mcolor"
    :class="[
      store.state.isTransparent,
      store.state.isRTL ? 'fixed-end' : 'fixed-start',
    ]"
    v-if="store.state.showSidenav"
  />
  <main
    class="main-content position-relative max-height-vh-100 h-100 border-radius-lg"
    :style="store.state.isRTL ? 'overflow-x: hidden' : ''"
  >
    <!-- nav -->
    <navbar
      :class="[navClasses]"
      :textWhite="store.state.isAbsolute ? 'text-white opacity-8' : ''"
      :minNav="navbarMinimize"
      v-if="store.state.showNavbar"
    />
    <router-view />
    <app-footer v-show="store.state.showFooter" />
    <configurator
      :toggle="toggleConfigurator"
      :class="[
        store.state.showConfig ? 'show' : '',
        store.state.hideConfigButton ? 'd-none' : '',
      ]"
    />
  </main>
</template>
