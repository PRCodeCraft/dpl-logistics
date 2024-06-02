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
        <div class="flex items-center pr-services-cardsgroup">
          <FontAwesomeIcon
            :icon="faChevronLeft"
            v-if="!isMobile"
            class="pr-chevron pr-chevron-left cursor-pointer"
            @click="previousCards"
          />
          <div class="pl-24 flex justify-center pr-cards">
            <template v-for="(card, index) in displayedCards" :key="index">
              <div class="pr-8 pr-single-card" :class="{ animate: isAnimating }">
                <img
                  :src="`./../src/assets/services/${card.image}`"
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
            v-if="!isMobile"
            class="pr-chevron pr-chevron-right cursor-pointer"
            @click="nextCards"
          />
        </div>
        <div class="flex justify-center pt-8">
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
      'A flatbed truck boasts an expansive, open loading area devoid of sides or a roof, tailored for transporting oversized and unconventional cargo. This design guarantees secure and efficient delivery, catering to the diverse needs of industries including construction, manufacturing, and logistics',
    image: 'flat_bed.png'
  },
  {
    title: 'Dry Van',
    description:
      'A dry van truck features an enclosed, box-like trailer designed to transport standard, non-perishable goods. It offers protection from weather and external elements, ensuring secure and efficient delivery. This type of truck is widely used in industries for the safe transportation',
    image: 'dry_van.jpg'
  },
  {
    title: 'Box Truck',
    description:
      'A box truck has a rigid, enclosed cargo area that resembles a box. It is designed for transporting various goods, offering protection from weather and external elements. This truck type ensures secure, efficient delivery and is widely used in retail, moving, and logistics industries',
    image: 'box_truck.jpg'
  },
  {
    title: 'Hotshot',
    description:
      'A hotshot truck, renowned for its agility, is designed for urgent deliveries. It typically comprises a heavy-duty pickup with a flatbed trailer. These trucks cater to industries like oil and gas, construction, and agriculture, providing rapid transport for smaller loads',
    image: 'hotshot.png'
  },
  {
    title: 'Refrigerated',
    description:
      'A refrigerated truck, or reefer truck, transports perishable goods at controlled temperatures. Equipped with a refrigeration system, it ensures safe delivery of items. Reefer trucks serve crucial roles in food distribution, pharmaceuticals, and floral transportation',
    image: 'refrigerated.png'
  },
  {
    title: 'Heavy Haul',
    description:
      'A heavy haul truck is designed to transport oversized or overweight loads. It features specialized equipment and configurations to handle immense cargo weights. Heavy haul trucks play a critical role in industries like construction, mining, and infrastructure development',
    image: 'heavy_haul.png'
  }
])

const currentIndex = ref(0)
let isMobile = false
const cardsPerPage = ref(3)
const isAnimating = ref(false)

const updateCardsPerPage = () => {
  if (window.innerWidth < 1130 && window.innerWidth >= 900) {
    cardsPerPage.value = 2
    isMobile = false
  } else if (window.innerWidth < 900) {
    cardsPerPage.value = 6
    isMobile = true
  } else {
    cardsPerPage.value = 3
    isMobile = false
  }
}

// Llama a la función para actualizar el número de tarjetas al cargar la página
updateCardsPerPage()

// Actualiza el número de tarjetas al cambiar el tamaño de la pantalla
window.addEventListener('resize', updateCardsPerPage)

const previousCards = () => {
  currentIndex.value =
    (currentIndex.value - cardsPerPage.value + cards.value.length) % cards.value.length
  isAnimating.value = true
  setTimeout(() => {
    isAnimating.value = false
  }, 500)
}

const nextCards = () => {
  currentIndex.value = (currentIndex.value + cardsPerPage.value) % cards.value.length
  isAnimating.value = true
  setTimeout(() => {
    isAnimating.value = false
  }, 500)
}

const displayedCards = computed(() => {
  const startIndex = currentIndex.value
  return cards.value.slice(startIndex, startIndex + cardsPerPage.value)
})
</script>
<style scoped>
#background-services {
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

.pr-cards {
  flex-direction: unset;
}

.animate {
  animation: slideInFromLeft 0.5s ease-in-out;
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

@media (max-width: 1130px) {
  .overlap-box {
    width: 55em;
  }

  .pr-cards {
    padding-left: 2rem;
  }

  .pr-services-cardsgroup {
    justify-content: center;
  }
}

@media (max-width: 900px) {
  .overlap-box {
    width: 30em;
    height: 180em;
  }

  .pr-cards {
    flex-direction: column;
  }

  .pr-single-card {
    padding-bottom: 2rem;
  }

  .pr-services-title-1::after {
    padding-top: 70px;
  }
}

@media (max-width: 550px) {
  .overlap-box {
    width: 22em;
  }

  .px-24 {
    padding-left: 2rem;
    padding-right: 2rem;
  }

  .pr-services-title-1::after {
    left: 2rem;
  }
}

@media (max-width: 370px) {
  .overlap-box {
    width: 17em;
    height: 187em;
  }

  .pr-img-services {
    width: 230px;
  }

  .pl-24 {
    padding-left: 2rem;
  }

  .pr-card-services {
    width: 230px;
  }

  .px-24 {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}
</style>
