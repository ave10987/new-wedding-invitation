<template>
  <div class="header georgiai">
    <div class="flex-item green-text logo" @click.prevent="goHome">
      <span style="visibility: hidden">logo</span>
    </div>
    <div class="flex-item green-text" @click.prevent="goInvitation">Invitation</div>
    <div class="flex-item green-text" @click.prevent="goGallery">Gallery</div>
    <div class="flex-item green-text" @click.prevent="goLocation">Location</div>
  </div>
</template>
<script>
export default {
  name: 'Header',
  methods: {
    goHome() {
      this.$EventBus.$emit('moveSwiper', 0);
    },
    goInvitation() {
      this.$EventBus.$emit('moveSwiper', 1);
    },
    goGallery() {
      this.$EventBus.$emit('moveSwiper', 2);
    },
    goLocation() {
      this.$EventBus.$emit('moveSwiper', 3);
    },
  },
};
</script>

<style>
  .header {
    position: absolute;
    width: 100%;
    height: 50px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    background-color: #afb99b;
  }
  .header .flex-item {
    flex: 1 1 auto;
    line-height: 50px;
  }
  .header .logo {
    background-image: url('../../static/img/logo.png');
    background-size: contain;
    background-repeat: no-repeat;
    height: 30px;
    margin: 10px;
  }
</style>
