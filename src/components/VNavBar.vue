<script lang="ts">
import { ref } from 'vue';
export default {
  setup() {
    let showMenu = ref(false)
    const toggleNav = () => (showMenu.value = !showMenu.value)
    return { showMenu, toggleNav }
  },
  methods: {
    pageClass(current: string) {
      // Access the current route using this.$route.path
      const path = this.$route.path;
      // Determine the class based on the path
      if (path === current) {
        return 'pr-navbar-item-active';
      } else {
        return '';
      }
    }
  }
}
</script>

<template>
  <div class="pr-background-navbar">
    <nav class="container py-1 mx-auto md:flex md:justify-between md:items-center px-12 mx-auto max-w-screen-xl">
      <div class="flex items-center justify-between">
        <router-link to="/" class="text-xl font-bold text-gray-100 md:text-2xl"
          ><img src="../assets/dpllogo.png" alt="dpl logo" width="100" height="100" class="mt-3 mb-3">
        </router-link>
        <!-- Mobile menu button -->
        <div @click="toggleNav" class="flex md:hidden w-16">
          <button
            type="button"
            class="text-gray-100 hover:text-gray-400 focus:outline-none focus:text-gray-400"
          >
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <ul
        :class="showMenu ? 'flex' : 'hidden'"
        class="flex-col mt-8 space-y-4 md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0"
      >
        <li class="text-gray-100 pr-navbar-item relative">
          <router-link to="/" id="home" :class="pageClass('/')">Home</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative">
          <router-link to="/About" id="about" :class="pageClass('/About')">About us</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative">
          <router-link to="/Services" id="services" :class="pageClass('/Services')">Services</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative">
          <router-link to="/Carriers" id="carriers" :class="pageClass('/Carriers')">Carriers</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative">
          <router-link to="/Contact" id="contact" :class="pageClass('/Contact')">Contact us</router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<style>
.pr-background-navbar {
  background-color: var(--color-indigo-100);
}

.pr-navbar-item:hover, .pr-navbar-item:focus {
  color: var(--color-light-blue-lighter);
}

.pr-navbar-item-active {
    border-bottom: 2px solid var(--color-light-blue-lighter);
    padding-bottom: 2px;
  
}

.pr-navbar-item {
    font-family: MundialLight;
}

.pr-navbar-item:not(:has(.pr-navbar-item-active))::after  {
    content: "";
    position: absolute;
    left: 50%;
    bottom: 2px;
    width: 0;
    height: 2px;
    background: var(--color-light-blue-lighter);
    transition: all 0.45s;
}

.pr-navbar-item:hover::after, .pr-navbar-item:focus::after{
    width: calc(100% - 0.5rem);
    bottom: -2px;
    left: 0.25rem;
}

button {
  margin: 0 0 !important;
}

.py-1 {
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
}
</style>
