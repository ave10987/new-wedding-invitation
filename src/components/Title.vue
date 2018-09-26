<template>
  <div class="title georgiai">
    <div class="line"></div>
    <div class="text green-text">{{ text }}</div>
  </div>
</template>
<script>
export default {
  name: 'Title',
  props: [
    'text',
  ],
};
</script>
<style>
  .title {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 50px;
    flex-direction: column;
    font-size: 28px;
    height: 100px;
  }

  .title .line {
    width: 100px;
    height: 2px;
    background-color: #2c5320;
    margin-bottom: 10px;
  }
</style>
