<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key = item.id><img class="swiper-img" :src="item.imgUrl"></swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://img1.qunarzz.com/qs/1805/48/c43eae59b340a502.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://img1.qunarzz.com/qs/1804/d0/a0267b745341a102.jpg'
      }, {
        id: '0003',
        imgUrl: 'https://img1.qunarzz.com/qs/1805/87/cddf3f0837def902.jpg'
      }, {
        id: '0004',
        imgUrl: 'https://img1.qunarzz.com/qs/1805/34/767349dfccc2a702.jpg'
      }, {
        id: '0005',
        imgUrl: 'https://img1.qunarzz.com/qs/1805/68/a4ae72b9a3486602.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active //穿透scop限制
    background: #fff
  .wrapper //网速调成3g防抖动
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 100%
    .swiper-img
      width: 100%
      height: 100%
</style>
