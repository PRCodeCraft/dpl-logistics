<template>
  <div>
    <VHeroBlock imageUrl="./src/assets/hero_carrier.png" title="Carriers" optionalClass="pr-carrier-hero" />
    <div id="background-carriers">
      <div class="overlap-box">
        <div class="relative">
          <div class="px-24 py-12">
            <span class="pr-carriers-title-1 text-2xl font-bold text-gray-800">Carrier </span
            ><span class="pr-carriers-title-2 text-2xl font-bold text-blue-500">information</span>
          </div>
          <div class="px-24 pb-8 flex">
            <div class="pr-carriers-description text-gray-700">
              Join DPL Logistics as a carrier today. Sign up now to unlock exclusive opportunities
              and maximize your potential.
            </div>
            <div class="pr-carrier-group">
              <img src="../assets/carrier_group.png" alt="carrier group" />
            </div>
          </div>
        </div>
        <div class="px-24 pb-8">
          <div class="pr-requisites pr-carriers-requisites">Requisites</div>
          <ul class="mt-3">
            <li class="pr-carriers-bullet">
              <FontAwesomeIcon :icon="faTruck" class="mr-3"></FontAwesomeIcon>MC Number older than 1
              year
            </li>
            <li class="pr-carriers-bullet">
              <FontAwesomeIcon :icon="faTruck" class="mr-3"></FontAwesomeIcon>Out of service rating
              lower than 25 percent
            </li>
            <li class="pr-carriers-bullet">
              <FontAwesomeIcon :icon="faTruck" class="mr-3"></FontAwesomeIcon>Carrier must refrain
              from engaging in any freight brokerage activities
            </li>
          </ul>
        </div>
        <div class="px-24 pb-8">
          <div class="pr-carriers-container">
            <div class="pr-carriers-title">Do you match our requirements?</div>
            <p class="pr-carriers-text">
              Fill out our file below and send it back to us at
              <a href="mailto: sales@dpl-logistics.com" class="pr-carriers-email">Sales@dpl-logistics.com</a>
            </p>
            <div class="flex justify-center pt-8">
              <a
                :href="carrierPacket"
                target="_blank"
                class="inline-flex items-center justify-center px-5 py-3 pr-btn-request-quote"
                >Download file<FontAwesomeIcon
                  :icon="faFileArrowDown"
                  class="ml-3"
                ></FontAwesomeIcon
              ></a>
            </div>
          </div>
        </div>
        <div class="px-24 pb-8">
          <div class="pr-carriers-requisites">Have any doubt?</div>
          <p class="pr-carriers-doubt">
            Feel free to contact us at
            <FontAwesomeIcon :icon="faPhone" class="ml-1 mr-1"></FontAwesomeIcon
            ><a href="tel:+13039154272" class="pr-carriers-phone">+1 303 915-4272</a>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faTruck, faFileArrowDown, faPhone } from '@fortawesome/free-solid-svg-icons'
import carrierPacket from '@/assets/files/carrierPacket.pdf'
</script>
<style scoped>
.pr-background-image-hero {
  background-size: cover;
  background-position-y: -190px;
  background-position-x: unset;
}
#background-carriers {
  background-color: var(--color-light-gray-100);
}
.overlap-box {
  position: relative;
  top: -40px;
  width: 70em;
  height: 50em;
  border-radius: 15px;
  margin: auto;
  background-color: var(--color-white);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  z-index: 2;
}
.pr-carriers-title-1 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-indigo-100);
}
.pr-carriers-title-1:after {
  content: '';
  position: absolute;
  width: 7%;
  left: 6rem;
  padding-top: 40px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}
.pr-carriers-title-2 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-light-blue);
}
.pr-carriers-description {
  font-family: 'Mundial';
  font-weight: 600;
  color: var(--color-indigo-100);
  font-size: 18px;
  max-width: 35rem;
  margin-top: -1rem;
}
.pr-carriers-requisites {
  font-family: 'Mundial';
  font-size: 20px;
  font-weight: 600;
  padding-top: unset;
}
.pr-carriers-requisites::after {
  content: '';
  position: absolute;
  width: 9%;
  left: 6rem;
  padding-top: 30px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}
.pr-carriers-bullet {
  font-family: 'Mundial';
  font-size: 17px;
  font-weight: 400;
  color: var(--color-indigo-100);
  margin: 0.5rem 0;
}
.pr-carrier-group {
  width: 250px;
  position: absolute;
  right: 100px;
  top: 60px;
}
.pr-carriers-container {
  border: 2px solid var(--color-light-blue-lighter);
  padding: 2rem;
  background-color: #c594001a;
}
.pr-carriers-title {
  font-family: 'AkiraExpandedDemo';
  padding-bottom: 1rem;
}
.pr-carriers-text {
  font-family: 'Mundial';
  font-size: 17px;
}
.pr-carriers-email {
  padding-left: 0.2rem;
  font-family: 'AkiraExpandedDemo';
  color: var(--color-indigo-100);
  text-decoration: underline;
  font-size: 15px;
  word-break: normal;
}
.pr-carriers-doubt {
  font-family: 'Mundial';
  font-size: 17px;
  font-weight: 400;
  color: var(--color-indigo-100);
  margin: 0.5rem 0;
}
.pr-carriers-phone {
  font-family: 'AkiraExpandedDemo';
  color: var(--color-indigo-100);
  font-size: 15px;
}
.py-12 {
    padding-bottom: 2.1rem;
}
@media (max-width: 1130px) {
  .pr-background-image-hero {
    background-position-y: -80px;
  }
  .overlap-box {
    width: 55em;
  }
  .pr-carrier-group {
    width: 200px;
    right: 30px;
    top: 90px;
  }
  .pr-carriers-title-1::after {
    width: 10%;
  }
  .pr-carriers-requisites::after {
    width: 11.5%;
  }
}
@media (max-width: 900px) {
  .overlap-box {
    width: 30em;
    height: 55em;
  }
  .px-24 {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
  .pr-carriers-title-1::after {
    left: 1.5rem;
    width: 20%;
  }
  .pr-carriers-requisites::after {
    width: 21%;
    left: 1.5rem;
  }
  .pr-carrier-group {
    top: 160px;
  }
}

@media (max-width: 700px) {
  .pr-background-image-hero {
    background-position-x: -100px;
    background-position-y: -200px;
  }
}
@media (max-width: 550px) {
  .pr-background-image-hero {
    background-position-x: -300px;
    background-position-y: -200px;
  }
  .overlap-box {
    width: 22em;
    height: 73em;
  }
  .pr-carriers-title-1::after {
    width: 25%;
    top: 5rem;
  }
  .pr-requisites.pr-carriers-requisites {
    padding-top: 6rem;
  }
  .pr-carrier-group {
    top: 260px;
    right: 5rem;
  }
  .pr-carriers-requisites::after {
    width: 29%;
  }
}
@media (max-width: 370px) {
  .pr-background-image-hero {
    background-position-x: -380px;
  }
  .overlap-box {
    width: 17em;
    height: 77em;
  }
  .px-24 {
    padding-left: 1rem;
    padding-right: 1rem;
  }
  .pr-carriers-title-1::after {
    left: 1rem;
  }
  .pr-carriers-requisites::after {
    left: 1rem;
    width: 37%;
  }
  .pr-carrier-group {
    top: 290px;
    right: 2rem;
  }
  .pr-carriers-container[data-v-fc8709a5] {
    padding: 0.5rem;
  }
}
</style>
