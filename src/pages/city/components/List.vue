<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbotom">当前城市</div>
                <div class="botton-list">
                    <div class="botton-wrapper">
                        <div class="botton">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbotom">热门城市</div>
                <div class="botton-list">
                    <div class="botton-wrapper">
                        <div class="botton">北京</div>
                    </div>
                    <div class="botton-wrapper">
                        <div class="botton">北京</div>
                    </div>
                    <div class="botton-wrapper">
                        <div class="botton">北京</div>
                    </div>
                    <div class="botton-wrapper">
                        <div class="botton">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbotom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbotom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbotom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbotom">A</div>
                <div class="item-list">
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                    <div class="item border-bottom">阿拉尔</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
    name: 'CityLit',
    mounted () {
        this.scroll = new Bscroll(this.$refs.wrapper)

    }
}
</script>
<style lang='stylus' scoped>
    @import '~reset/varibles.styl';
    .border-topbotom
      &:before
          border-color :#ccc
      &:after
          border-color :#ccc
    .border-bottom
      &:before
          border-color :#ccc 
    .list
        overflow hidden
        position absolute
        top 1.68rem
        left 0
        right 0
        bottom 0
        // background red
        .title
            line-height .54rem
            font-size .26rem
            background #eee
            padding-left .2rem
            .border-topbotom
                color #666
        .botton-list
            overflow hidden
            padding .1rem .6rem .1rem .1rem

            .botton-wrapper
                width 33.33%
                float left
                .botton
                    padding .1rem 0
                    text-align center
                    margin .1rem
                    border .02rem solid #ccc
                    border-radius .06rem
        .item-list 
            .item
                line-height .76rem
                // color #666
                padding-left .2rem
            




</style>
