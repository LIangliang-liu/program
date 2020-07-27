<template>
     <div class="wrapper">
         <swiper :options="swiperOption" v-if="showSwiper">
           <swiper-slide v-for="item of list" :key="item.id">
             <div class="img-wrap">
                  <img class="swiper-img" :src="item.imgUrl" />
             </div>
           </swiper-slide>
           <div class="swiper-pagination" slot="pagination"></div>
         </swiper>
     </div>
</template>

<script>
export default {
    name:'HomeSwiper',
    props:{
        list:Array
    },
    data (){
        return {
            swiperOption:{
                pagination:'.swiper-pagination',
                loop:true
            }
        }
    },
    computed:{
        showSwiper (){
            return this.list.length
        }
    }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>>.swiper-pagination-bullet-active
    background :#fff
  .wrapper
    width :100%
    background:#eee
    .swiper-img
      width :100%
</style>