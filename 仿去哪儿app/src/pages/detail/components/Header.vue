<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-back">&#xe646;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe646;</div>
      </router-link>
    景点详情
    </div>
  </div>
</template>

<script>
export default {
  name:'DetailHeader',
  data() {
    return {
        showAbs:true,
        opacityStyle:{
          opacity:0
        }
    }
  },
  methods:{
    handleScroll (){
      const top=document.documentElement.scrollTop
      if(top > 60){ 
        let opacity = top / 140
        opacity = opacity>1 ?1:opacity
        this.opacityStyle = {opacity}
        this.showAbs = false
      }else{
        this.showAbs = true
      }
    }
  },
  activated (){
    window.addEventListener('scroll',this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  .header-abs
    position :absolute
    left:.2rem
    top:.2rem
    width :.6rem
    height :.6rem
    line-height :.6rem
    text-align :center
    border-radius :.3rem
    background :rgba(0,0,0,0.5)
    .header-abs-back
      color :#fff
      font-size.4rem
  .header-fixed
    position :fixed
    top:0
    left :0
    right:0
    height :.8rem
    line-height :.8rem
    background :#00bcd4
    text-align :center
    font-size: .32rem
    color:#fff
    .header-fixed-back
      position :absolute
      left :0
      top :0
      width :.8rem
      text-align :center
      font-size:.4rem
      color :#fff
</style>