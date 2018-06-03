<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item of list" :key = item.id><img class="swiper-img" :src="item.imgUrl"></swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active //穿透scop限制
    background: #fff
  .wrapper >>> .swiper-container-horizontal
    height: 31.25vh
  .wrapper //网速调成3g防抖动
    overflow: hidden
    width: 100%
    height: 31.25vh
    .swiper-img
      width: 100%
      height: 100%
</style>
