<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <li class="item border-buttom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:"HomeRecommend",
    data () {
        return {
            recommendList:[{
                id:"0001",
                imgUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
                title:"东方闪电尽快付款",
                desc:"士大夫"
            },
            {
                id:"0002",
                imgUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
                title:"东方闪电尽快付款",
                desc:"士大夫"
            },
            {
                id:"0003",
                imgUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
                title:"东方闪电尽快付款",
                desc:"士大夫"
            }]
        }

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
