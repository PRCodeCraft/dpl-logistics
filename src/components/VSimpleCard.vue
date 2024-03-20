<template>
  <div :class="[baseClass, { 'cursor-pointer': isLink }, optionalClass]" class="pr-background-simple-card" >
    <div v-if="isLink">
      <a :href="link">
        <h5 class="mb-2 text-2xl font-bold tracking-tight pr-title-text-sc">
          {{ title }}
        </h5>
        <p class="font-normal pr-content-text-sc">{{ content }}</p>
      </a>
    </div>
    <div v-else>
      <div>
        <h5 class="mb-2 text-2xl font-bold tracking-tight pr-title-text-sc">
          {{ title }}
        </h5>
        <p class="font-normal pr-content-text-sc">{{ content }}</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    content: {
      type: String,
      required: true
    },
    isLink: {
      type: Boolean,
      default: true,
      required: true
    },
    link: {
      type: String,
      default: '#'
    },
    optionalClass: {
      type: String,
      required: false,
    },
  },
  computed: {
    baseClass() {
      return 'pr-container-simple-card p-6 bg-white border border-gray-200 rounded-lg shadow'
    }
  }
}
</script>
<style>
.cursor-pointer {
    cursor: pointer;
}

.pr-background-simple-card {
    background-color: var(--color-light-blue-lighter-plus);
}

.pr-container-simple-card {
    height: 11rem;
    width: 28rem;
}

.pr-title-text-sc, .pr-content-text-sc  {
    font-family: MundialLight;
    color: var(--color-indigo-100);
}
</style>
