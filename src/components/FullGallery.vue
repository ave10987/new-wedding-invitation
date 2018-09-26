<template>
  <swiper :options="gallerySwiperOption" class="full-screen-swiper" :style="{ height: `${galleryHeight}px` }">
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/1.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/2.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/3.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/4.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/5.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/6.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/7.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/8.jpg" alt="">
      </div>
    </swiper-slide>
    <swiper-slide @click.prevent.stop>
      <div>
        <img src="../../static/img/9.jpg" alt="">
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
export default {
  name: 'FullGallery',
  props: [
    'selectedImageIdx',
  ],
  data() {
    return {
      gallerySwiperOption: {
        spaceBetween: 30,
        effect: 'coverflow',
        grabCursor: true,
        loop: true,
        zoom: false,
        lazy: {
          loadPrevNext: true,
          loadPrevNextAmount: 2,
        },
        centeredSlides: true,
        coverflowEffect: {
          rotate: 50,
          stretch: 0,
          depth: 100,
          modifier: 1,
          slideShadows: true,
        },
      },
    };
  },
  computed: {
    galleryHeight() {
      return window.document.documentElement.clientHeight * 0.9;
    },
  },
  mounted() {
    const gallerySwiper = document.querySelector('.full-screen-swiper.swiper-container').swiper;
    gallerySwiper.slideTo(parseInt(this.selectedImageIdx, 10) + 1, 0);
    gallerySwiper.on('resize', () => {
      this.clientHeight = document.documentElement.clientHeight;
    });
  },
};
</script>

<style>
.full-screen-swiper {
  width: 100%;
}
.full-screen-swiper .swiper-slide {
  background-size: contain;
  background-repeat: no-repeat;
  text-align: center;
  padding: 10px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  background-color: transparent!important;
  justify-content: space-around!important;
}

.full-screen-swiper div {
  position: relative;
  height: 100%;
}

.full-screen-swiper img {
  width: 100%;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin: auto;
}
</style>
