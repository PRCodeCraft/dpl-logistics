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
                We aspire to be recognized as the premier symbol of excellence and reliability in
                the trucking industry, committed to being your steadfast and trusted logistics
                partner.
              </div>
          </div>
        </div>
      </div>
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

@media(max-width: 1207px) {
  .pr-display-home {
   flex-direction: column-reverse;
  }

  .pr-mission-check, .pr-vision-check {
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

@media(max-width: 725px) {
  .pr-image-ms-home {
    width: 300px;
  }
}

@media(max-width: 625px) {
  .px-20 {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}

@media(max-width: 500px) {
  .pr-image-ms-home {
    width: 250px;
  }
  .p-12 {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
}

@media(max-width: 400px) {
  .pr-image-ms-home {
    width: 200px;
  }
}

@media(max-width: 350px) {
  .pr-image-ms-home {
    width: 150px;
  }
}
</style>
