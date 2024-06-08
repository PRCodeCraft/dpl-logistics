<script setup lang="ts">
import VMountain from '@/components/VMountain.vue'
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faCheck } from '@fortawesome/free-solid-svg-icons'
import VSimpleCard from '@/components/VSimpleCard.vue'
</script>

<template>
  <VHeroBlock
    imageUrl="./src/assets/hero_home.png"
    title="DPL LOGISTICS"
    description="We deliver superior truckload services, exceeding client expectations"
    buttonText="Contact Us"
    buttonRouteName="/Contact" />
  <!-- Mision & Vision section  -->
  <div class="pr-background-brand py-36 px-20">
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
    <div class="flex justify-between pr-freight-direction">
      <div class="pr-text-btn-freight mx-auto">
        <div class="pr-text-freight">
          Do you have freight that requires
          <span class="pr-middle-text-freight">prompt and reliable</span> transportation?
        </div>
        <router-link
          to="/Contact"
          class="inline-flex items-center justify-center px-5 py-3 pr-btn-hero"
          >Give us a call</router-link
        >
      </div>
      <img src="../assets/lorryHome2.jpg" alt="lorry on the road" class="pr-image-freight-home" />
    </div>
  </div>
  <!-- Why choose us section  -->
  <div class="py-16 pr-background-request-quote">
    <div class="flex justify-center mb-16 pr-title-choose-us">Why choose us ?</div>
    <div class="flex justify-center">
      <div class="pr-content-choose-us">
        What set us apart is our seasoned expertise as brokers with over a decade of experience,
        ensuring we understand the precise trucking solutions needed to fulfill your requirements
        with utmost professionalism.
      </div>
    </div>
    <div class="grid grid-cols-2 justify-items-stretch gap-x-8 gap-y-8">
      <div class="pr-odd-simple-card">
        <VSimpleCard
          title="Dependable service"
          content="We take pride in our commitment to reliability. Count on us for punctual deliveries and transparent, consistent communication."
          :is-link="false"
        />
      </div>
      <div class="pr-even-simple-card">
        <VSimpleCard
          title="Safety first"
          content="Your cargo’s safety is our top priority. Our drivers undergo rigorous training and strictly adhere to safety protocols, ensuring the secure transportation of your goods."
          :is-link="false"
        />
      </div>
      <div class="pr-odd-simple-card">
        <VSimpleCard
          title="Flexible solutions"
          content="Regardless of your load’s size or complexity, we offer customized flatbed solutions to meet your transportation needs effectively."
          :is-link="false"
        />
      </div>
      <div class="pr-even-simple-card">
        <VSimpleCard
          title="Nationwide reach"
          content="From coast to coast, our efficient flatbed shipping solutions cover the entire country. Benefit from our extensive network, providing reliable service across diverse geographical locations."
          :is-link="false"
        />
      </div>
    </div>
    <div class="flex justify-center pt-16">
      <router-link
        to="/Contact"
        class="inline-flex items-center justify-center px-5 py-3 pr-btn-request-quote"
        >Request a quote</router-link
      >
    </div>
  </div>
  <!-- Truck icons section  -->
  <div class="pr-background-truck-icons">
    <div class="flex justify-center mb-16 pr-title-choose-us pt-24">Services offered</div>
    <div class="flex justify-center">
      <div class="pr-content-choose-us">
        Experience a comprehensive range of logistics options tailored to meet your diverse
        transportation needs.
      </div>
    </div>
    <div class="grid grid-cols-3 mx-auto pr-truck-container-max-width gap-y-8 gap-x-8 pb-8">
      <div class="pr-truck-icon-odd">
        <div class="pr-truck-icon-max-width">
          <img
            src="../assets/iconTrucks/icons_flat_bed.png"
            alt="flat bed truck icon"
            width="180"
          />
        </div>
        <div class="pr-title-truck-icon">Flat Bed</div>
        <div class="pr-description-truck-icon">Versatile solutions for various cargo types</div>
      </div>
      <div class="pr-truck-icon-even">
        <div class="pr-truck-icon-max-width">
          <img src="../assets/iconTrucks/icons_dry_van.png" alt="dry van truck icon" width="180" />
        </div>
        <div class="pr-title-truck-icon">Dry Van</div>
        <div class="pr-description-truck-icon">Efficient transportation with enclosed storage</div>
      </div>
      <div class="pr-truck-icon-odd">
        <div class="pr-truck-icon-max-width">
          <img
            src="../assets/iconTrucks/icons_box_truck.png"
            alt="box truck truck icon"
            width="180"
          />
        </div>
        <div class="pr-title-truck-icon">Box Truck</div>
        <div class="pr-description-truck-icon">
          Tailored for partial truck shipments when a full 53 dry van is not required
        </div>
      </div>
      <div class="pr-truck-icon-even">
        <div class="pr-truck-icon-max-width">
          <img src="../assets/iconTrucks/icons_hot_shot.png" alt="hotshot truck icon" width="180" />
        </div>
        <div class="pr-title-truck-icon">Hotshot</div>
        <div class="pr-description-truck-icon">Swift and dedicated expedited services</div>
      </div>
      <div class="pr-truck-icon-odd">
        <div class="pr-truck-icon-max-width">
          <img
            src="../assets/iconTrucks/icons_refrigerated.png"
            alt="refrigerated truck icon"
            width="180"
          />
        </div>
        <div class="pr-title-truck-icon">Refrigerated</div>
        <div class="pr-description-truck-icon">
          Prioritized, expedited shipping for urge deliveries
        </div>
      </div>
      <div class="pr-truck-icon-even">
        <div class="pr-truck-icon-max-width">
          <img src="../assets/iconTrucks/truck-icon.png" alt="heavy haul truck icon" width="180" />
        </div>
        <div class="pr-title-truck-icon">Heavy haul</div>
        <div class="pr-description-truck-icon">Loads that weight more than 80,000 lbs, gross weight or require permits to move</div>
      </div>
    </div>
    <div class="flex justify-center pt-16 pb-24">
      <router-link
        to="/Services"
        class="inline-flex items-center justify-center px-5 py-3 pr-btn-request-quote"
        >Services</router-link
      >
    </div>
  </div>
        <!-- Mountain section  -->
        <VMountain />
  <!-- Dakota image section  -->
  <div class="pr-background-image-dakota">
    <div class="pr-img-container-dakota pt-24 pb-24">
      <img src="../assets/Dakota.png" alt="vp logistic owner" width="620" height="620" class="pr-img-dakota" />
    </div>
  </div>
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
  padding-left: 6.5rem;
  padding-bottom: unset;
  padding-right: 1rem;
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

.pr-background-request-quote {
  background: linear-gradient(rgba(255, 255, 255, 0.9), rgba(255, 255, 255, 0.9)),
    url('../assets/neumatic.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}

.pr-title-choose-us {
  font-family: AkiraExpandedDemo;
  color: var(--color-indigo-100);
  font-size: 20px;
  position: relative;
}

.pr-title-choose-us:after {
  content: '';
  position: absolute;
  width: 5%;
  padding-top: 40px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}

.pr-content-choose-us {
  font-family: AkiraExpandedDemo;
  color: var(--color-indigo-100);
  font-size: 12px;
  max-width: 38rem;
  padding-bottom: 4rem;
  text-align: center;
}

.pr-odd-simple-card {
  display: flex;
  justify-content: flex-end;
}

.pr-even-simple-card {
  display: unset;
  justify-content: unset;
}

.pr-btn-request-quote {
  font-family: AkiraExpandedDemo;
  color: var(--color-white);
  background-color: var(--color-indigo-100);
  font-size: unset;
}

.pr-btn-request-quote:hover,
.pr-btn-request-quote:focus {
  color: var(--color-indigo-80);
  background-color: var(--color-gray-100);
}

.pr-truck-container-max-width {
  max-width: 65rem;
}

.pr-background-truck-icons {
  background-color: var(--color-light-blue-lighter-plus);
}

.pr-truck-icon-max-width {
  max-width: 300px;
  display: flex;
  justify-content: center;
}

.pr-title-truck-icon {
  max-width: 300px;
  font-family: Mundial;
  font-weight: 900;
  font-size: 20px;
  display: flex;
  justify-content: center;
}

.pr-description-truck-icon {
  max-width: 300px;
  font-family: MundialLight;
  font-size: 16px;
  display: flex;
  text-align: center;
  justify-content: center;
}

.pr-truck-icon-odd,
.pr-truck-icon-even {
  display: unset;
  justify-content: unset;
}

.pr-background-image-dakota {
  background-image: url('../assets/wallpaper2.png');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-blend-mode:darken;

}

.pr-img-container-dakota {
  display: flex;
  justify-content: center;
}

.pr-img-dakota {
  border: 5px solid var(--color-light-blue-intense);
  -webkit-filter: drop-shadow(5px 5px 5px #666666);
  filter: drop-shadow(5px 5px 5px #666666);
}

.pr-vp-text {
  font-family: MundialLight;
  font-size: 18px;
  color: var(--color-indigo-100);
  font-weight: 600;
}

@media (max-width: 1280px) {
  .pr-text-btn-freight {
    padding-left: 3rem;
  }
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

  .py-36 {
    padding-top: 5rem;
    padding-bottom: 5rem;
  }
}

@media (max-width: 1050px) {
  .grid-cols-3 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .pr-truck-icon-odd {
    display: grid;
    justify-content: flex-end;
  }
}

@media (max-width: 1018px) {
  .pr-text-freight {
    font-size: 20px;
  }
}

@media (max-width: 1000px) {
  .grid-cols-2 {
    grid-template-columns: repeat(1, minmax(0, 1fr));
  }
  .pr-odd-simple-card,
  .pr-even-simple-card {
    display: flex;
    justify-content: center;
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
    padding-bottom: 3rem;
  }
}

@media (max-width: 725px) {
  .pr-image-ms-home {
    width: 300px;
  }

  .pr-btn-request-quote {
    font-size: 12px;
  }
}

@media (max-width: 700px) {
  .grid-cols-3 {
    grid-template-columns: repeat(1, minmax(0, 1fr));
  }
  .pr-truck-icon-even,
  .pr-truck-icon-odd {
    display: grid;
    justify-content: center;
  }
}

@media (max-width: 635px) {
  .pr-title-choose-us {
    font-size: 15px;
  }

  .pr-content-choose-us {
    font-size: 10px;
    max-width: 30rem;
  }

  .pr-btn-request-quote {
    font-size: 10px;
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

  .pr-content-choose-us {
    max-width: 22rem;
  }

  .pr-title-text-sc {
    font-size: 18px;
  }

  .pr-content-text-sc {
    font-size: 14px;
  }

  .pr-container-simple-card {
    width: 22rem;
    height: 12rem;
  }
}

@media (max-width: 400px) {
  .pr-image-ms-home {
    width: 200px;
  }

  .pr-container-simple-card {
    width: 18rem;
    height: 13rem;
  }

  .pr-content-choose-us {
    max-width: 18rem;
  }
}

@media (max-width: 382px) {
  .pr-text-freight {
    font-size: 17px;
  }

  .pr-text-btn-freight {
    padding-left: 1rem;
  }
}

@media (max-width: 350px) {
  .pr-image-ms-home {
    width: 150px;
  }

  .pr-truck-icon-max-width,
  .pr-title-truck-icon,
  .pr-description-truck-icon {
    max-width: 280px;
  }
}

@media (max-width: 300px) {
  .pr-container-simple-card {
    width: 17rem;
    height: 13rem;
  }

  .pr-content-choose-us {
    max-width: 17rem;
  }
}
</style>