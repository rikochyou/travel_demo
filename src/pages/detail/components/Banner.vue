<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg"/>
      <div class = "banner-info">
        <div class = "banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe604;</span>
          {{this.bannerImgs.length}}</div>
      </div>
    </div>
    <fade>
      <common-gallery :imgs="bannerImgs" v-show="showGallery" @close= "handleGalleyClose"></common-gallery>
    </fade>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import Fade from 'common/fade/Fade'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallery: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleGalleyClose () {
      this.showGallery = false
    }
  },
  components: {
    CommonGallery,
    Fade
  }
}
</script>

<style scoped lang="stylus">
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        padding: 0 .4rem
        line-height: .32rem
        margin-top: .14rem
        height: .32rem
        border-radius: .2rem
        font-size: .24rem
        background: rgba(0, 0, 0, .8)
</style>
