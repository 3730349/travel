<template>
  <div class="header">
      <div class="header-left">
          <div class="iconfont back-icon">&#xe682;</div>
      </div>
      <div class="header-input">
          <span class="iconfont">&#xe643;</span>
          输入城市/景点/游玩主题
          </div>
      <div class="header-right">
          {{this.city}}
          <span class="iconfont">&#xe6aa;</span>
          </div>
  </div>
</template>

<script>
export default {
  name: 'HoemHeader',
  props: {
      city: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
    @import '~reset/varibles.styl';
    *
        padding 0
        margin 0
    .header
        line-height .86rem
        background red
        display flex
        font-size .3rem
        background $bgColor
        color #fff
        .header-left
            width .64rem
            float left
            .back-icon
                text-align center
                font-size .4rem

        .header-input
            flex 1
            height .64rem
            line-height .64rem
            margin-top .12rem
            margin-left .2rem
            padding-left .2rem
            background #ffffff
            border-radius .1rem
            color #ccc
        .header-right
            width 1.24rem
            float right
            text-align center


</style>
