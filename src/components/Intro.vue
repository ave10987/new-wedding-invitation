<template>
  <div class="page-wrapper intro">
    <Header />
    <div class="content-wrapper">
      <Title :text="'Save the Date'" />
      <div class="description flex-item">
        <div class="korean time">10월 28일(일) 2PM</div>
        <div class="korean location">양재역 브라이드 밸리</div>
      </div>
      <div class="name flex-item">
        <span class="green-text korean">최정민</span>
        <img src="../../static/img/heart.png" alt="">
        <span class="green-text korean">윤정현</span>
      </div>
      <div class="photo flex-item">
        <img src="../../static/img/main.png" alt="">
      </div>
    </div>
  </div>
</template>
<script>
import Header from './Header';
import Title from './Title';

export default {
  name: 'Intro',
  components: {
    Header,
    Title,
  },
};
</script>
<style>
  .intro .content-wrapper .description {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .intro .content-wrapper .description .time {
    font-size: 26px;
    font-weight: 800;
    margin: 10px 0;
  }
  .intro .content-wrapper .description .location {
    font-size: 20px;
    font-weight: 400;
    margin: 10px 0;
  }
  .intro .content-wrapper .name {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    margin: 0 30px;
  }
  .intro .content-wrapper .name span {
    font-size: 20px;
    font-weight: 800;
    flex: 1 1 auto;
    text-align: center;
  }
  .intro .content-wrapper .name img {
    width: 40px;
  }
  .intro .content-wrapper .photo {
    margin: 0 10px;
  }
  .intro .content-wrapper .photo img {
    width: 100%;
  }
</style>
