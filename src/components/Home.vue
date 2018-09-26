<template>
  <div class="container">
    <div class="dimmed" v-if="isGalleryOpen" @click.prevent.stop="closeGallery">
      <span @click.prevent="closeGallery" style="background-size: contain; background-image: url('../../static/image/close.png'); width: 30px; height: 30px; float: right; margin: 10px;"></span>
      <FullGallery :selectedImageIdx="selectedImageIdx"/>
    </div>
    <swiper class="swiper-wrapper" :options="mainSwiperOption">
      <div class="parallax-bg" slot="parallax-bg" data-swiper-parallax="-23%"></div>
      <swiper-slide class="slide-flex">
        <Intro />
      </swiper-slide>
      <swiper-slide class="slide-flex">
        <Invitation />
      </swiper-slide>
      <swiper-slide class="slide-flex">
        <Gallery />
      </swiper-slide>
      <swiper-slide class="slide-flex">
        <Location />
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
import Intro from './Intro';
import Invitation from './Invitation';
import Location from './Location';
import Gallery from './Gallery';
import FullGallery from './FullGallery';

export default {
  name: 'Home',
  components: {
    Intro,
    Invitation,
    Location,
    Gallery,
    FullGallery,
  },
  data() {
    return {
      mainSwiperOption: {
        parallax: true,
        fade: true,
        lazy: {
          loadPrevNext: true,
          loadPrevNextAmount: 1,
        },
      },
      isGalleryOpen: false,
      selectedImageIdx: 0,
    };
  },
  methods: {
    closeGallery() {
      this.isGalleryOpen = false;
    },
  },
  mounted() {
    this.$EventBus.$on('galleryOpen', (index) => {
      this.isGalleryOpen = true;
      this.selectedImageIdx = index;
    });

    this.$EventBus.$on('moveSwiper', (index) => {
      document.querySelector('.swiper-container').swiper.slideTo(index);
    });
  },
};
</script>

<style>
  .slide-flex {
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>

