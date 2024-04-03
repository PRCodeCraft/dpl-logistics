<template>
  <div>
    <VHeroBlock imageUrl="./src/assets/hero_services.png" title="Services" />
    <div id="background-services">
      <div class="overlap-box">
        <div class="px-24 py-12">
          <span class="pr-services-title-1 text-2xl font-bold text-gray-800">Services </span
          ><span class="pr-services-title-2 text-2xl font-bold text-blue-500">offered</span>
        </div>
        <div class="px-24 pb-8">
          <div class="pr-services-description text-gray-700">
            Experience a comprehensive range of logistics options tailored to meet your diverse
            transportation needs.
          </div>
        </div>
        <div class="flex items-center">
          <FontAwesomeIcon
            :icon="faChevronLeft"
            class="pr-chevron pr-chevron-left cursor-pointer"
            @click="previousCards"
          />
          <div class="pl-24 flex">
            <template v-for="(card, index) in displayedCards" :key="index">
              <div class="pr-8" :class="{ animate: isAnimating }">
                <img
                  :src="`/src/assets/services/${card.image}`"
                  :alt="card.title"
                  class="pr-img-services"
                />
                <div class="pr-card-services">
                  <div class="pr-title-card-services">{{ card.title }}</div>
                  <div class="pr-description-card-services">{{ card.description }}</div>
                </div>
              </div>
            </template>
          </div>
          <FontAwesomeIcon
            :icon="faChevronRight"
            class="pr-chevron pr-chevron-right cursor-pointer"
            @click="nextCards"
          />
        </div>
        <div class="flex justify-center pt-16">
          <router-link
            to="/Contact"
            class="inline-flex items-center justify-center px-5 py-3 pr-btn-request-quote"
            >Request a quote</router-link
          >
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faChevronLeft, faChevronRight } from '@fortawesome/free-solid-svg-icons'
import { computed, ref } from 'vue'

const cards = ref([
  {
    title: 'Flat Bed',
    description:
      'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diamonu. My nibh euismod tinci dunt utaoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam',
    image: 'flat_bed.png'
  },
  {
    title: 'Dry Van',
    description:
      'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diamonu. My nibh euismod tinci dunt utaoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam',
    image: 'dry_van.jpg'
  },
  {
    title: 'Box Truck',
    description:
      'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diamonu. My nibh euismod tinci dunt utaoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam',
    image: 'box_truck.jpg'
  },
  {
    title: 'Hotshot',
    description:
      'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diamonu. My nibh euismod tinci dunt utaoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam',
    image: 'hotshot.png'
  },
  {
    title: 'Refrigerated',
    description:
      'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diamonu. My nibh euismod tinci dunt utaoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam',
    image: 'refrigerated.png'
  },
  {
    title: 'Heavy Haul',
    description:
      'Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diamonu. My nibh euismod tinci dunt utaoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam',
    image: 'heavy_haul.png'
  }
])

const currentIndex = ref(0)

const cardsPerPage = 3
const isAnimating = ref(false)

const previousCards = () => {
  currentIndex.value = (currentIndex.value - cardsPerPage + cards.value.length) % cards.value.length
  isAnimating.value = true
  setTimeout(() => {
    isAnimating.value = false
  }, 500)
}

const nextCards = () => {
  currentIndex.value = (currentIndex.value + cardsPerPage) % cards.value.length
  isAnimating.value = true
  setTimeout(() => {
    isAnimating.value = false
  }, 500)
}

const displayedCards = computed(() => {
  const startIndex = currentIndex.value
  return cards.value.slice(startIndex, startIndex + cardsPerPage)
})
</script>
<style scoped>
#background-services {
  background-color: var(--color-light-gray-100);
}
.overlap-box {
  position: relative;
  top: -40px;
  width: 70%;
  height: 47em;
  border-radius: 15px;
  margin: auto;
  background-color: var(--color-white);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  z-index: 2;
}

.pr-services-title-1 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-indigo-100);
}

.pr-services-title-1:after {
  content: '';
  position: absolute;
  width: 7%;
  left: 6rem;
  padding-top: 40px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}

.pr-services-title-2 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-light-blue);
}

.pr-services-description {
  font-family: 'Mundial';
  font-weight: 600;
  color: var(--color-indigo-100);
  font-size: 18px;
  max-width: 35rem;
  margin-top: -1rem;
}

.pr-chevron {
  font-family: 'Mundial';
  font-size: 30px;
  font-weight: 600;
  position: absolute;
  top: 50%;
}

.pr-img-services {
  width: 270px;
  height: 170px;
}

.pr-card-services {
  width: 270px;
  background-color: var(--color-light-gray-100);
}

.pr-chevron-left {
  left: 2.5rem;
}

.pr-chevron-right {
  right: 2.5rem;
}

.pr-title-card-services {
  font-family: 'Mundial';
  font-size: 16px;
  font-weight: 600;
  color: var(--color-indigo-100);
  padding-left: 0.6rem;
  padding-right: 0.6rem;
  padding-top: 0.6rem;
}

.pr-description-card-services {
  font-family: 'Mundial';
  font-size: 14px;
  color: var(--color-indigo-100);
  padding-left: 0.6rem;
  padding-right: 0.6rem;
  padding-top: 0.6rem;
  padding-bottom: 1.3rem;
}

@keyframes slideInFromLeft {
  0% {
    transform: translateX(-3%);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

.animate {
  animation: slideInFromLeft 0.5s ease-in-out;
}
</style>
