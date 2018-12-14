<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <router-link 
            tag="li"
            class="item border-buttom" 
            v-for="item of list" 
            :key="item.id"
            :to="'/detail/'+ item.id"
            >
                <img class="item-img" :src="item.imgUrl">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </router-link>
        </ul>
    </div>
</template>
<script>
export default {
    name:"HomeRecommend",
    props: {
        list: Array
    }
}
</script>
<style lang="stylus" scoped>
    @import '~reset/mixins.styl';
    .title
        margin-top 0.1rem
        line-height .7rem
        background #eee
        font-size 0.3rem
    .item
        overflow hidden
        height 1.9rem
        display flex
        // background red
        font-size 0.3rem
        .item-img
            height 1.7rem
            width 1.7rem
            padding 0.1rem
        .item-info
            flex 1
            padding .1rem
            min-width 0
            .item-title
                line-height .54rem
                font-size .32rem
                ellipsis()
            .item-desc
                line-height .4rem
                color #ccc
                ellipsis()
            .item-button
                margin-top .2rem
                background #ff9300
                padding  0 .2rem
                border-radius .06rem
                color #fff



</style>
