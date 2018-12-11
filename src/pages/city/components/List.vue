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
                    <div class="botton-wrapper" 
                    v-for="item of hot" 
                    :key="item.id">
                        <div class="botton">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div 
                class="area" 
                v-for="(item , key) of cities" 
                :key='key'
                :ref='key'
                >
                <div class="title border-topbotom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom" 
                    v-for="innerItem of item" 
                    :key="innerItem.id">
                    {{innerItem.name}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
    name: 'CityLit',
    props: {
        hot: Array,
        cities: Object,
        letter: String
    },
    mounted () {
        this.scroll = new Bscroll(this.$refs.wrapper)

    },
    //监听， 点击右侧的字母时跳到相应的城市
    watch: {
        letter() {
            if(this.letter) {
                const element = this.$refs[this.letter][0]
                this.scroll.scrollToElement(element)
            }
        }
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
