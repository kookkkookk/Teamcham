<template>
  <div id="swiper">
    <div id="container">
      <swiper :options="swiperOption" ref="mySwiper">
        <swiper-slide class="swiper-slide games banner1"><img src="../../assets/images/banner01.jpg"></swiper-slide>
        <swiper-slide class="swiper-slide games banner2"><img src="../../assets/images/banner02.jpg"></swiper-slide>
        <swiper-slide class="swiper-slide games banner3"><img src="../../assets/images/banner03.jpg"></swiper-slide>
      </swiper>
      <!-- <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div> -->
      <div class="swiper-pagination" slot="pagination"></div>
    </div>
  </div>
</template>
<script>
  import { swiper, swiperSlide } from 'vue-awesome-swiper'
  export default {
    name: 'banner',
    data () {
      return {
        swiperOption: {
          //notNextTick: true,
          // swiper configs 所有的配置同swiper官方api配置
          // autoplay: 3000,
          loop: true,
          //prevButton: '.swiper-button-prev',
          //nextButton: '.swiper-button-next'
          slidesPerView: 'auto',//非撐滿，而是使用圖片大小，所以會露出其他slider banner圖
          centeredSlides: true,//上述的置中
          // spaceBetween: 30, //間隔
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          }
        }
      }
    },
    components: {
      swiper,
      swiperSlide
    },
    methods: {

    },
    mounted(){
      
      if(document.body.clientWidth > 1300){
          this.swiperOption.slidesPerView = "auto";
      }else{
          this.swiperOption.slidesPerView = 1;
      }

      /*window.onresize = function(event){
        // console.log("resize")
        if(document.body.clientWidth > 1300){
          //this.swiperOption.centeredSlides = true
        }else{
          //this.swiperOption.centeredSlides = false
        }
      }*/
    }
  }
</script>

<style type="text/scss" lang="scss">
  @import '../../assets/scss/_mixin.scss';
  html {
    background: rgba(0,0,0,.5);
  }
  // #swiper {
  //   position: relative;
  //   width: 100%;
  //   height: 700px;
  //   min-width: 1280px;
  //   background: #d3d6a2;
  //   #container {
  //     width: 60%;
  //     height: 300px;
  //     margin: 0 auto;
  //     position: relative;
  //     top: 50%;
  //     transform: translateY(-50%);
  //   }
    .swiper-slide {
      width: 1280px;
      // height: 700px;
      // background-size: cover;
      // &.banner1{
      //   background-image: url('../../assets/images/banner01.jpg');
      // }
      // &.banner2{
      //   background-image: url('../../assets/images/banner02.jpg');
      // }
      // &.banner3{
      //   background-image: url('../../assets/images/banner03.jpg');
      // }
      @include SCREEN_1300{
        width: 100%;
      }
      img{
        width: 100%;
      }
    }
    .swiper-pagination{
      left: 0;
      right: 0;
      margin-top: 10px;
      >span{
        margin: 0 8px;
        width: 12px;
        height: 12px;
        position: relative;
      }
      >span.swiper-pagination-bullet-active{
        background: #84a2b3;
      }
      

      >span::after{
        content:"";
        width: 6px;
        height: 6px;
        display: block;
        background-color: #ededed;
        border-radius: 3px;
        position: absolute;
        top: 3px;
        left: 3px;;
      }
      >span.swiper-pagination-bullet-active::after{
        background-color: #84a2b3;
      }
    }
  // }
</style>