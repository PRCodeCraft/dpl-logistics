<script lang="ts">
import { ref } from 'vue';
import dpllogo from '../assets/dpllogo.png';
let navbarItemArray = ['home', 'about', 'contact', 'services', 'carrier']
export default {
  setup() {
    let showMenu = ref(false)
    const toggleNav = () => (showMenu.value = !showMenu.value)
    return { showMenu, toggleNav }
  },
  methods: {
    updateNavBarItem(item: any) {
      document.querySelectorAll('.pr-navbar-item-active').forEach((e) => {
        e.classList?.remove('pr-navbar-item-active')
      })
      navbarItemArray.forEach((e) => {
        if (e === item) {
          document.getElementById(item)?.classList.add('pr-navbar-item-active')
        }
      })
    }
  },
  created() {
    setTimeout(() => {
      this.updateNavBarItem('home')
    }, 200);
  }
}
</script>

<template>
  <div class="pr-background-navbar">
    <nav class="container px-6 py-1 mx-auto md:flex md:justify-around md:items-center">
      <div class="flex items-center justify-around">
        <router-link to="/" class="text-xl font-bold text-gray-100 md:text-2xl"
          ><img src="../assets/dpllogo.png" alt="dpl logo" width="150" height="150" class="mt-3 mb-3">
        </router-link>
        <!-- Mobile menu button -->
        <div @click="toggleNav" class="flex md:hidden">
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
        <li class="text-gray-100 pr-navbar-item relative" @click="updateNavBarItem('home')">
          <router-link to="/" id="home">Home</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative" @click="updateNavBarItem('about')">
          <router-link to="/About" id="about">About us</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative" @click="updateNavBarItem('contact')">
          <router-link to="/Contact" id="contact">Contact us</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative" @click="updateNavBarItem('services')">
          <router-link to="/Services" id="services">Services</router-link>
        </li>
        <li class="text-gray-100 pr-navbar-item relative" @click="updateNavBarItem('carrier')">
          <router-link to="/Carrier" id="carrier">Carrier</router-link>
        </li>
      </ul>
    </nav>
  </div>
</template>

<style>
.pr-background-navbar {
  background-color: var(--color-indigo);
}

.pr-navbar-item:hover, .pr-navbar-item:focus {
  color: var(--color-light-blue-lighter);
}

.pr-navbar-item-active {
    border-bottom: 2px solid var(--color-light-blue-lighter);
    padding-bottom: 2px;
  
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
</style>
