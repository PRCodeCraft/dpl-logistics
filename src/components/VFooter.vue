<script setup>
import { ref } from 'vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faEnvelope, faPhone } from '@fortawesome/free-solid-svg-icons'

const currentYear = ref(new Date().getFullYear())
</script>

<template>
  <footer class="pr-background-footer shadow">
    <div class="my-1 w-full mx-auto max-w-screen-xl p-4 md:flex md:items-center md:justify-between">
      <span class="text-sm pr-text-dpl-footer sm:text-center"
        >© {{ currentYear }} <a href="#" class="hover:underline">DPL Logistics</a>. All Rights
        Reserved.</span
      >
      <ul
        class="flex flex-wrap items-center text-sm font-medium mt-0 gap-x-8"
      >
        <li class="flex pr-text-footer items-center gap-1">
          <FontAwesomeIcon :icon="faEnvelope" class="pr-icon-footer"/>
          <a href="mailto: sales@dpl-logistics.com">sales@dpl-logistics.com</a>
        </li>
        <li class="pr-text-footer"><FontAwesomeIcon :icon="faPhone" class="pr-icon-footer"/>+1 303 915-4272</li>
      </ul>
    </div>
  </footer>
</template>

<style>
.pr-icon-footer{
  color: var(--color-light-blue-lighter);
}

.pr-text-dpl-footer, .pr-text-footer{
  font-weight: 600;
  color: var(--color-white);
}

.pr-background-footer{
  background-color: var(--color-indigo-100);
}
</style>
