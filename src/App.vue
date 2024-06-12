<script setup lang="ts">
import VNavBar from './components/VNavBar.vue';
import VFooter from './components/VFooter.vue';
</script>

<template>
  <main>
    <VNavBar/>
    <div class="pr-main-content">
      <!-- No funciona bien el transition -->
      <!-- <Transition name="slide" mode="out-in">
        <component :is="Component"></component>
      </Transition> -->
      <RouterView v-slot="{ Component }">
        <component :is="Component"></component>
      </RouterView>
    </div>
    <a href="https://wa.me/+13039154272/?text=Hi, I would like to..." className="pr-app-whatsapp" target="_blank" rel="noopener noreferrer">
        <img src="https://res.cloudinary.com/dajm6vubw/image/upload/v1693269359/RBespacios/whatsapp-icon_ycnnhn.png" alt="whatsapp icon"/>
      </a>
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

.pr-main-content {
  background-color: var(--color-light-gray-100);
}

.pr-app-whatsapp{
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 2;
  width: 4em;
}

@media (max-width: 900px) {
  .pr-app-whatsapp{
    width: 3em;
  }
}

@media (max-width: 500px) {
  .pr-app-whatsapp{
    width: 2em;
  }
}
</style>
