<script setup lang="ts">
import VNavBar from './components/VNavBar.vue';
import VFooter from './components/VFooter.vue';
</script>

<template>
  <main>
    <VNavBar/>
    <div>
      <!-- No funciona bien el transition -->
      <!-- <Transition name="slide" mode="out-in">
        <component :is="Component"></component>
      </Transition> -->
      <RouterView v-slot="{ Component }">
        <component :is="Component"></component>
      </RouterView>
    </div>
    <VFooter/>
  </main>
</template>

<style scoped>

.slide-enter-active, .slide-leave-active {
  transition: all 0.3s ease-in-out;
}

.slide-enter-from {
  opacity: 0;
  transform: translateX(-100%); /* Slide in from the left */
}

.slide-leave-to {
  opacity: 0;
  transform: translateX(100%);  /* Slide out to the right */
}

.slide-enter-to, .slide-leave-from {
  opacity: 1;
  transform: translateX(0);
}

</style>
