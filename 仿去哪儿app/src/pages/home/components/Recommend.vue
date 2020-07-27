<template>
    <div>
        <div class="title">
            <img  class="like-img" src="https://imgs.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" >
            <span class="like-title">猜你喜欢</span>
        </div>
        <ul>
            <router-link tage="li" class="item" 
            v-for="item of list" :key="item.id" :to="'./detail/' +item.id">
                <div class="item-img-wrap">
                  <img class="item-img" :src="item.imgUrl">
                  <div class="mp-like-tag" :style="{backgroundImage:'url(' + item.tagImgUrl + ')'}">{{item.tag}}</div>
                </div>
                <div class="item-info">
                  <p class="item-title">{{item.title}}</p>
                  <div class="item-like-comment">
                    <span class="startlevel">{{item.startlevel}}</span>
                    <span class="comment-num">{{item.commentNum}}条评论</span>
                  </div>
                  <div class="like-price">
                    <span class="price">¥<em class="price-num">{{item.priceNum}}</em></span>起
                    <span class="like-address">{{item.address}}</span>
                  </div>
                  <p class="item-feature">{{item.feature}}</p>
                </div>
            </router-link>
        </ul>
        <a class="item-more" href="" onclick="return false">查看所有产品</a>
    </div>
</template>

<script>
export default {
    name:'HomeRecommend',
    props:{
      list:Array
    }
}
</script>

<style lang="stylus" scoped>
    .title
      height :0.84rem
      border-top: .2rem solid #eee 
      line-height :.84rem
      .like-img
        display: inline-block;
        overflow: hidden;
        width: .3rem;
        height: .3rem;
        margin-left: .2rem;
      .like-title
        font-size: .32rem;
    .item
      position: relative
      overflow :hidden
      display :flex
      height :2.4rem
      margin-left:.3rem
      padding: .1rem 0
      .item-img
        position :relative
        width :2rem
        height :2rem
      .mp-like-tag 
        position: absolute
        top: 0.1rem
        left: 0
        width: 1.02rem
        height: .38rem
        background-size: 100%
        color: #fff
        font-size: .2rem
        line-height: .38rem
        text-indent :.04rem
      .item-info
        height 2.5rem
        margin-left :.2rem
        flex:1
        .item-title
          margin-top: .26rem
          height: .44rem
          color: #212121
          font-size: .32rem
          line-height: .44rem
        .item-like-comment
          margin-top: .14rem
          height: .34rem
          .startlevel
            color:orange
          .comment-num
            margin-left:.3rem
        .like-price
            position: relative
            margin-top: .1rem
            color: #616161
            font-size: .24rem
            line-height: .4rem
            .price
              color: #ff8300
            .price-num
              color: #ff8300
              font-size :.4rem  
            .like-address
              float :right
              font-size:.25rem
              margin-right:.2rem
        .item-feature
            display: inline-block
            margin-top: .1rem;
            margin-right: .24rem
            background: #fff9f9
            padding: .04rem .1rem
            color: #f55
            font-size: .24rem
            line-height: .34rem
    .item-more
      border-top: .01rem solid #eee
      display: block;
      padding: .2rem 0;
      color: #00afc7;
      font-size: .28rem;
      line-height: .4rem;
      text-align: center;                  
</style>