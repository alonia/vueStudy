<template lang="html">
  <mt-swipe :auto="4000">
    <mt-swipe-item><div class="one">1</div></mt-swipe-item>
    <mt-swipe-item><div class="two">2</div></mt-swipe-item>
    <mt-swipe-item><div class="three">3</div></mt-swipe-item>
  </mt-swipe>
</template>

<script>
export default {

  props:['swiperData']

}
</script>

<style lang="less" scoped>

.mint-swipe {
  width: 100%;
  height:50vw;
  a,img {
    display: block;
    width: 100%;
    height:100%;
  }
}
.one{
  background-color:#ccc;
  width:100%;
  height:100%;
}
.two{
  background:yellow;
  width:100%;
  height:100%;
}
.three{
  background:green;
  width:100%;
  height:100%;
}
</style>
