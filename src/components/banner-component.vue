<style>
  .banner-component>.margin{height: 460px;background-color: blueviolet;position: relative}
  .banner-component>.margin .swiper-container {
    width: 100%;
    height: 100%;
  }
  .banner-component>.margin .swiper-slide {
    text-align: center;
    font-size: 18px;
    background: #fff;
    height: 460px;

    /* Center slide text vertically */
    display: -webkit-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    -webkit-align-items: center;
    align-items: center;
  }
  .banner-component>.margin .swiper-slide:nth-child(1){background-image: url("./../assets/images/banner/banner0.jpg")}
  .banner-component>.margin .swiper-slide:nth-child(2){background-image: url("./../assets/images/banner/banner1.jpg")}
  .banner-component>.margin .swiper-slide:nth-child(3){background-image: url("./../assets/images/banner/banner2.jpg")}
</style>

<template>
  <div class="banner-component">
    <div class="margin">
      <!-- Swiper -->
      <div class="swiper-container">
        <div class="swiper-wrapper">
          <div class="swiper-slide"></div>
          <div class="swiper-slide"></div>
          <div class="swiper-slide"></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import Swiper from 'swiper'
  export default {
    mounted(){
      var swiper = new Swiper('.swiper-container');
    }
  }
</script>
