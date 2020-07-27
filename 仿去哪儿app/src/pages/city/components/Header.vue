<template>
    <div class="header">
        <router-link to="/">
            <div class="header-left">
                <div class="iconfont home-back">&#xe646;</div>
            </div>
        </router-link>
        <div class="header-right">城市选择</div>
    </div>
</template>
<script>
export default {
    name:'CityHeader'
}
</script>

<style lang="stylus" scoped>
    .header
      position :relative
      overflow :hidden
      height :.86rem
      line-height :.86rem
      background :#00bcd4
      text-align :center
      font-size: .32rem
      color:#fff
      .home-back
       position :absolute
       left :0
       top :0
       width :.8rem
       text-align :center
       font-size:.4rem
       color :#fff
</style>