<script lang="ts" setup>

const props = defineProps({
    imageUrl: { 
      type: String, 
      required: true, 
      default: '' 
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: false
    },
    buttonRouteName: {
      type: String,
      default: ''
    },
    buttonText: {
      type: String,
      default: ''
    }
});
</script>


<template>
  <section
    class="pr-background-image-hero" :style="{ backgroundImage: `url(${imageUrl})` }">
    <div class="grid max-w-screen-xl px-12 py-16 mx-auto lg:py-32">
      <div class="mr-auto place-self-center lg:col-span-5 pr-max-width-hero">
        <h1
          class="mb-4 text-2xl pr-hero-block-font tracking-tight leading-none sm:max-w-xl sm:text-3xl md:max-w-xl md:text-4xl lg:text-5xl lg:max-w-2xl">
          {{ title }}
        </h1>
        <p class="mb-6 pr-hero-block-description-font sm:max-w-xl md:text-1xl lg:mb-8 lg:text-2xl lg:max-w-2xl">
          {{ description }}
        </p>
        <router-link v-if="buttonText" :to="props.buttonRouteName"
          class="inline-flex items-center justify-center px-5 py-3 pr-btn-hero">
          {{ buttonText }}
        </router-link>
      </div>
    </div>
  </section>
</template>

<style>
.pr-background-image-hero {
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

.pr-btn-hero {
  font-family: AkiraExpandedDemo;
  color: var(--color-indigo-100);
  background-color: var(--color-white);
  font-size: unset;
}

.pr-btn-hero:hover,
.pr-btn-hero:focus {
  color: var(--color-indigo-80);
  background-color: var(--color-gray-100);
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