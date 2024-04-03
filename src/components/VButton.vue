<template>
  <router-link v-if="isInternal" :to="to" :class="computedClasses">
    <span>{{ buttonText }}</span>
    <span v-if="hasIcon" class="mr-2">
      <font-awesome-icon :icon="faCheck" />
    </span>
  </router-link>
  <a v-else :href="to" :class="computedClasses" target="_blank">
    <span>{{ buttonText }}</span>
    <span v-if="hasIcon" class="mr-2">
      <font-awesome-icon :icon="faCheck" />
    </span>
  </a>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faCheck } from '@fortawesome/free-solid-svg-icons'
export default {
  components: {
    FontAwesomeIcon
  },
  props: {
    to: {
      type: [String, Object],
      default: null
    },
    hasIcon: {
      type: Boolean,
      default: false
    },
    icon: {
      type: String,
      default: null
    },
    buttonText: {
      type: String,
      default: "Button"
    }
  },
  computed: {
    computedClasses() {
      return [
        "inline-flex items-center justify-center px-5 py-3 pr-btn-hero",
      ];
    },
    isInternal() {
      // Detecta si la URL es interna o externa
      return typeof this.to === 'string' && this.to.startsWith('/');
    }
  }
};
</script>

<style>
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
</style>
