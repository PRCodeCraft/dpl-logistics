<template>
  <div class="about">
    <VHeroBlock imageUrl="./src/assets/hero_services.png" title="About Us" />
    <div class="background-about">
      <div class="overlap-box">
        <div class="px-24 py-12">
          <span class="pr-about-title-1 text-2xl font-bold text-gray-800">Our </span
          ><span class="pr-about-title-2 text-2xl font-bold text-blue-500">history</span>
        </div>
        <article>
          Rooted in a robust history of hands-on experience within a distinguished freight company, my
professional journey led me to establish our own venture during the challenging times of the
COVID era. Our company's inception was fueled by a strategic vision to reshape conventional
approaches and infuse a new dimension of value into the logistics landscape. The decision to
launch our company during such unprecedented times was not just a response to challenges but
a testament to our unwavering belief in the transformative power of expertise.
        </article>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
</script>

<style>
.background-about {
  background-color: var(--color-light-gray-100);
}

.overlap-box {
  position: relative;
  top: -40px;
  width: 70em;
  height: 47em;
  border-radius: 15px;
  margin: auto;
  background-color: var(--color-white);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  z-index: 2;
}

.pr-about-title-1 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-indigo-100);
}

.pr-about-title-1:after {
  content: '';
  position: absolute;
  width: 7%;
  left: 6rem;
  padding-top: 40px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}

.pr-about-title-2 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-light-blue);
}

article {
  font-family: 'Mundial';
  font-weight: 100;
  font-size: 18px;
  color: var(--color-indigo-80);
  padding: 0 6em;
}
</style>
