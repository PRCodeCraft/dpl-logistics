<script lang="ts">
  export default {
    name: 'VMountain',
  }
</script>

<template>
  <div class="relative">
    <div class="flex justify-center pr-img-logo-container">
      <div class="pr-logo-between-img"></div>
    </div>
    <img src="../assets/sky.png" class="pr-img-sky" />
    <img src="../assets/mountains.png" class="pr-img-mountains" />
  </div>
</template>

<style>
.pr-img-sky {
  position: relative;
  z-index: 0;
  width: 100%;
  min-height: 30vh;
}

.pr-logo-between-img {
  background-image: url(../assets/logonegro.png);
  background-repeat: no-repeat;
  background-position-x: center;
  background-size: 550px;
  height: 100%;
  width: 100%;
  background-attachment: fixed;
  position: absolute;
  z-index: 1;
  -webkit-filter: drop-shadow(5px 5px 5px #666666);
  filter: drop-shadow(5px 5px 5px #666666);
}

.pr-img-mountains {
  position: absolute;
  bottom: 0;
  z-index: 2;
  width: 100%;
  height: 50%;
  -webkit-filter: drop-shadow(5px 5px 5px #666666);
  filter: drop-shadow(5px 5px 5px #666666);
}

@media (max-width: 1430px) {
  .pr-logo-between-img {
    background-size: 350px;
  }
}

@media (max-width: 900px) {
  .pr-logo-between-img {
    background-size: 250px;
  }
}

@media (max-width: 767px) {
  .pr-logo-between-img {
    background-size: 150px;
  }
}

@media (max-width: 500px) {
  .pr-logo-between-img {
    background-size: 100px;
  }
}

@media (max-width: 365px) {
  .pr-logo-between-img {
    background-size: 80px;
  }
}
</style>
