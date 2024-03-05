<script setup lang="ts">
import VMountain from '../components/VMountain.vue'
import VHeroBlock from '../components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faCheck } from '@fortawesome/free-solid-svg-icons'
</script>

<template>
  <VHeroBlock />
  <!-- Mision & Vision section  -->
  <div class="pr-background-brand py-24 px-20">
    <div class="pr-background-white">
      <div class="pr-display-home mx-auto max-w-screen-xl">
        <div class="p-12 pr-display-img-mv">
          <img src="../assets/lorryHome.jpg" alt="lorry in road" class="pr-image-ms-home" />
        </div>
        <div class="p-12">
          <div>
            <span class="pr-mission-text">Mission</span
            ><span class="pr-vision-text"> & Vision</span>
          </div>
          <div class="pt-12">
            <div class="flex pr-mission-check">
              <font-awesome-icon :icon="faCheck" class="pr-check-one" />
              We consistently deliver superior truckload services, exceeding client expectations
              through reliability, efficiency, and a relentless commitment to excellence in every
              aspect of our logistics solutions.
            </div>
            <div class="flex pr-vision-check pt-8">
              <font-awesome-icon :icon="faCheck" class="pr-check-two" />
              We aspire to be recognized as the premier symbol of excellence and reliability in the
              trucking industry, committed to being your steadfast and trusted logistics partner.
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- Freight - give us a call section  -->
  <div class="pr-background-freight">
    <div class="flex justify-end gap-x-14 pr-freight-direction">
      <div class="pr-text-btn-freight">
        <div class="pr-text-freight">
          Do you have freight that requires
          <span class="pr-middle-text-freight">prompt and reliable</span> transportation?
        </div>
        <router-link
          to="/contact"
          class="inline-flex items-center justify-center px-5 py-3 pr-btn-hero"
          >Give us a call</router-link
        >
      </div>
      <img src="../assets/lorryHome2.jpg" alt="lorry on the road" class="pr-image-freight-home" />
    </div>
  </div>
  <VMountain />
</template>

<style>
.pr-background-brand {
  background-image: url('../assets/PatronDeMarca.jpg');
}

.pr-background-white {
  background-color: var(--color-white);
  border-radius: 8px;
}

.pr-display-home {
  display: flex;
  flex-direction: unset;
}

.pr-image-ms-home {
  width: 400px;
  height: auto;
  border-radius: 8px;
}

.pr-mission-text {
  font-family: AkiraExpandedDemo;
  color: var(--color-indigo-100);
  border-bottom: 2px solid var(--color-light-blue);
  padding-bottom: 10px;
}

.pr-vision-text {
  font-family: AkiraExpandedDemo;
  color: var(--color-light-blue);
}

.pr-check-one {
  background-color: var(--color-indigo-100);
  border-radius: 50%;
  padding: 0.3rem;
  color: var(--color-white);
}

.pr-check-two {
  background-color: var(--color-light-blue);
  border-radius: 50%;
  padding: 0.3rem;
  color: var(--color-white);
}

.pr-mission-check,
.pr-vision-check {
  font-family: MundialLight;
  max-width: 35rem;
  column-gap: 1rem;
}

.pr-background-freight {
  background: url('../assets/PatronDeMarca2.jpg');
  background-color: var(--color-indigo-100);
  background-blend-mode: multiply;
  background-size: contain;
}

.pr-freight-direction {
  flex-direction: unset;
}

.pr-image-freight-home {
  width: 500px;
  height: auto;
}

.pr-text-btn-freight {
  margin-left: auto;
  padding-left: 3rem;
  padding-bottom: unset;
  padding-right: unset;
}

.pr-text-freight {
  font-family: AkiraExpandedDemo;
  color: var(--color-light-blue);
  font-size: 30px;
  max-width: 50rem;
  margin-top: 1.9rem;
  margin-bottom: 1.9rem;
}

.pr-middle-text-freight {
  color: var(--color-light-blue-lighter);
}

@media (max-width: 1260px) {
  .pr-text-freight {
    font-size: 25px;
  }
}

@media (max-width: 1207px) {
  .pr-display-home {
    flex-direction: column-reverse;
  }

  .pr-mission-check,
  .pr-vision-check {
    max-width: 55rem;
  }

  .pr-display-img-mv {
    display: flex;
    justify-content: center;
  }

  .p-12 {
    padding-top: 1rem;
  }
}

@media (max-width: 1018px) {
  .pr-text-freight {
    font-size: 20px;
  }
}

@media (max-width: 871px) {
  .pr-text-freight {
    font-size: 20px;
  }

  .pr-freight-direction {
    flex-direction: column;
  }

  .pr-image-freight-home {
    width: auto;
  }

  .pr-text-btn-freight {
    margin-left: unset;
    padding-bottom: 3rem;
    padding-right: 3rem;
  }
}

@media (max-width: 725px) {
  .pr-image-ms-home {
    width: 300px;
  }
}

@media (max-width: 625px) {
  .px-20 {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}

@media (max-width: 500px) {
  .pr-image-ms-home {
    width: 250px;
  }
  .p-12 {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
}

@media (max-width: 400px) {
  .pr-image-ms-home {
    width: 200px;
  }
}

@media (max-width: 382px) {
  .pr-text-freight {
    font-size: 17px;
  }

  .pr-text-btn-freight {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}

@media (max-width: 350px) {
  .pr-image-ms-home {
    width: 150px;
  }
}
</style>
