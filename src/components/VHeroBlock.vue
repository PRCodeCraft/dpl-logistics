<script lang="ts">
import VButton from '@/components/VButton.vue';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faCheck } from '@fortawesome/free-solid-svg-icons'   
  export default {
    name: 'VHeroBlock',
    components: {
    VButton,
    FontAwesomeIcon,
    faCheck,
  },
  }
</script>

<template>
  <section class="pr-background-image-hero">
    <div class="grid max-w-screen-xl px-12 py-16 mx-auto lg:py-32">
      <div class="mr-auto place-self-center lg:col-span-5 pr-max-width-hero">
        <h1
          class="mb-4 text-2xl pr-hero-block-font tracking-tight leading-none sm:max-w-xl sm:text-3xl md:max-w-xl md:text-4xl lg:text-5xl lg:max-w-2xl"
        >
          Reliable trucking solutions
        </h1>
        <p
          class="mb-6 pr-hero-block-description-font sm:max-w-xl md:text-1xl lg:mb-8 lg:text-2xl lg:max-w-2xl"
        >
          Specializing in truckload services with precision, efficiency, and a commitment to timely,
          quality deliveries
        </p>
        <router-link
          to="/Contact"
          class="inline-flex items-center justify-center px-5 py-3 pr-btn-hero"
          >Contact us</router-link
        >
        <VButton to="/Contact" hasIcon="true" icon="faCheck" buttonText="Contact us"/>
      </div>
    </div>
  </section>
</template>

<style>
.pr-background-image-hero {
  background-image: url('../assets/hero_home.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
}

.pr-hero-block-font {
  font-family: AkiraExpandedDemo;
  color: var(--color-white);
}

.pr-hero-block-description-font {
  font-family: Mundial;
  font-weight: 900;
  color: var(--color-light-blue-lighter);
}

.pr-max-width-hero {
  max-width: unset;
}

@media (max-width: 1024px) {
  .pr-hero-block-description-font {
    font-size: 18px;
  }
}

@media (max-width: 767px) {
  .pr-max-width-hero {
    max-width: 26rem;
  }

  .pr-btn-hero {
    font-size: 12px;
  }

  .pr-hero-block-description-font {
    font-size: 15px;
  }
}

@media (max-width: 640px) {
  .pr-btn-hero {
    font-size: 10px;
  }
}

@media (max-width: 483px) {
  .pr-max-width-hero {
    max-width: 22rem;
  }

  .pr-hero-block-description-font {
    font-size: 13px;
  }

  .pr-hero-block-font {
    font-size: 1.3rem;
  }
}

@media (max-width: 382px) {
  .pr-hero-block-description-font {
    font-size: 11px;
  }

  .pr-hero-block-font {
    font-size: 1.1rem;
  }

  .px-12 {
    padding-left: 1rem;
    padding-right: 1rem;
  }
}
</style>
