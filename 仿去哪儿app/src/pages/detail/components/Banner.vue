<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/2006/79/7941d4e788e10832a3.img.jpg_600x330_474c2fe2.jpg">
      <div class="banner-info">
        <div class="banner-title">宋城千古情</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe721;</span>24</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name:'DetailBanner',
  data (){
    return {
        showGallary:false,
        imgs:["http://img1.qunarzz.com/sight/p0/2006/79/7941d4e788e10832a3.img.jpg_600x330_474c2fe2.jpg",
           "http://img1.qunarzz.com/sight/p0/2006/fc/fca224064616b2f1a3.img.jpg_r_800x800_9c293189.jpg"
          ]
    }
  },
  methods:{
      handleBannerClick (){
          this.showGallary=true
      },
      handleGallaryClose (){
          this.showGallary=false
      } 
  },
  components:{
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position :relative
    overflow :hidden
    height :0
    padding-bottom:55%
   .banner-img
      width :100%
   .banner-info
      display :flex
      position :absolute
      left :0
      right :0
      bottom :0
      padding-left:.4rem
      line-height:.6rem
      color :#fff
      background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
     .banner-title
       flex:1
       font-size:.36rem
     .banner-number
       height :.4rem
       width :1.2rem
       line-height .4rem
       border-radius :.2rem
       background :rgba(0,0,0, .4)
       text-align :center
       font-size:.24rem
       .banner-icon
         font-size:.24rem
         padding-right:.1rem
</style>