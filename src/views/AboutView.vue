<template>
  <div class="about">
    <VHeroBlock
      imageUrl="./src/assets/hero_about.png"
      title="About Us"
      optionalClass="pr-hero-about-position"
    />
    <div class="background-about">
      <div class="overlap-box">
        <div class="px-24 py-12">
          <span class="pr-about-title-1 text-2xl font-bold text-gray-800">Our </span
          ><span class="pr-about-title-2 text-2xl font-bold text-blue-500">history</span>
        </div>
        <article>
          <p>
            Rooted in a robust history of hands-on experience within a distinguished freight
            company, my professional journey led me to establish our own venture during the
            challenging times of the COVID era. Our company's inception was fueled by a strategic
            vision to reshape conventional approaches and infuse a new dimension of value into the
            logistics landscape. The decision to launch our company during such unprecedented times
            was not just a response to challenges but a testament to our unwavering belief in the
            transformative power of expertise.
          </p>
          <div class="pr-article-quote">
            Emphasizing value addition, my deep industry understanding became our approach’s
            cornerstone.
          </div>
          <p>Amid global uncertainties, our commitment to excellence stood firm.</p>
          <div class="pr-article-images">
            <img src="../assets/office_image_1.jpg" alt="" class="img-1" />
            <img src="../assets/office_image_2.jpg" alt="" class="img-2" />
            <img src="../assets/office_image_3.jpg" alt="" class="img-3" />
          </div>
          <p>
            In conclusion, our venture's inception reflects our unwavering belief in
            expertise-driven transformation and commitment to excellence. Rooted in industry
            insights, we aim to reshape logistics with personalized, customer-centric solutions.
          </p>
          <a href="/Contact" class="contact-button">
            <button>Request a quote</button>
            <span class="icon-container">
              <FontAwesomeIcon :icon="faArrowRight" class="pr-icon-arrow" />
            </span>
          </a>
        </article>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import VHeroBlock from '@/components/VHeroBlock.vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faArrowRight } from '@fortawesome/free-solid-svg-icons'
</script>

<style>
.pr-hero-about-position {
  background-position-y: -17rem;
}
.background-about {
  background-color: var(--color-light-gray-100);
}

.overlap-box {
  position: relative;
  top: -40px;
  width: 70em;
  height: max-content;
  border-radius: 15px;
  margin: auto;
  background-color: var(--color-white);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  z-index: 2;
}

.pr-about-title-1 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-indigo-100);
}

.pr-about-title-1:after {
  content: '';
  position: absolute;
  width: 7%;
  left: 6rem;
  padding-top: 40px;
  border-bottom: 2px solid var(--color-light-blue-lighter);
}

.pr-about-title-2 {
  font-family: 'AkiraExpandedDemo';
  font-size: 25px;
  color: var(--color-light-blue);
}

article {
  padding: 0 6em 3em 6em;
}

article p {
  font-size: 18px;
  color: var(--color-indigo-60);
}

.pr-article-quote {
  font-family: 'Mundial';
  font-weight: 600;
  font-size: 26px;
  padding-left: 1.2em;
  margin: 2em 0;
  border-left: solid 2px var(--color-light-blue);
}

.pr-article-images {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  grid-template-areas: 'img-1 img-1' 'img-2 img-3';
  gap: 1em;
  margin: 3em 0;
}

.img-1 {
  width: 100%;
  height: 25em;
  object-fit: cover;
  grid-area: img-1;
  object-position: bottom;
}

.img-2 {
  height: 100%;
  object-fit: cover;
  grid-area: img-2;
}

.img-3 {
  height: 100%;
  object-fit: cover;
  grid-area: img-3;
}

button {
  padding: 1em;
  padding-left: 2em;
  background-color: #1d2344;
  font-family: AkiraExpandedDemo;
  color: white;
  border: none;
  width: 20em;
  text-align: left;
  border-radius: 0px;
  cursor: pointer;
  margin: 2em 0;
}

.contact-button {
  display: flex;
}

.pr-icon-arrow {
  transform: translate(-45px, 37px);
  color: white;
  font-size: 1.5em;
  padding-top: 0.35em;
}

@media (max-width: 1130px) {
  .overlap-box {
    width: 55em;
  }

  .pr-article-images {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-template-areas: 'img-1' 'img-2' 'img-3';
    gap: 1em;
    margin: 3em 0;
  }

  .pr-article-images img {
    height: auto;
    width: 100%;
    object-fit: contain;
  }

  .contact-button button {
    display: flex;
    width: 20em;
  }
}

@media (max-width: 900px) {
  .overlap-box {
    width: 38em;
    height: 145em;
  }

  article {
    padding: 0 2em 3em 2em;
  }

  .px-24 {
    padding-left: 2em;
    padding-right: 2em;
  }

  .pr-about-title-1:after {
    left: 2rem;
    width: 10%;
  }

  .pr-article-images {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-template-areas: 'img-1' 'img-2' 'img-3';
    gap: 1em;
    margin: 3em 0;
  }

  .pr-article-images img {
    height: auto;
    width: 100%;
    object-fit: contain;
  }
}

@media (max-width: 620px) {
  .overlap-box {
    width: 28em;
    height: 130em;
  }

  .pr-hero-about-position {
    background-position-x: -950px;
  }

  .pr-article-images {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-template-areas: 'img-1' 'img-2' 'img-3';
    gap: 1em;
    margin: 3em 0;
  }

  .pr-about-title-1:after {
    width: 15%;
  }

  .pr-article-images img {
    height: auto;
    width: 100%;
    object-fit: contain;
  }

  .contact-button {
    display: flex;
    text-align: center;
  }

  .pr-article-quote {
    font-size: 20px;
    padding-left: 1em;
  }
}

@media (max-width: 445px) {
  .overlap-box {
    width: 20em;
    height: 140em;
  }

  .pr-about-title-1:after {
    width: 20%;
  }

  .contact-button {
    padding: 1rem;
    font-size: 12px;
  }

  .contact-button button {
    padding: 1rem;
  }

  .pr-icon-arrow {
    display: none;
  }
}

@media (max-width: 330px) {
  .overlap-box {
    width: 17em;
    height: 155em;
  }

  .pr-about-title-1:after {
    padding-top: 70px;
  }

  .contact-button {
    padding: 1rem;
    font-size: 10px;
  }

  .contact-button button {
    padding: 1rem;
  }
}
</style>
