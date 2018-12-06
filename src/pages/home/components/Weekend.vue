<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-buttom" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <!-- <button class="item-button">查看详情</button> -->
                </div>
                
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:"HomeWeekend",
    data () {
        return {
            recommendList:[{
                id:"0001",
                imgUrl:"https://img1.qunarzz.com/vc/a4/36/26/07c5904b545d66b3abe72e9dfa.jpg",
                title:"东方闪电尽快付款",
                desc:"士大夫"
            },
            {
                id:"0002",
                imgUrl:"https://img1.qunarzz.com/vc/a4/36/26/07c5904b545d66b3abe72e9dfa.jpg",
                title:"东方闪电尽快付款",
                desc:"士大夫"
            },
            {
                id:"0003",
                imgUrl:"https://img1.qunarzz.com/vc/a4/36/26/07c5904b545d66b3abe72e9dfa.jpg",
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
        font-size 0.3rem
        .item-img-wrapper
            overflow hidden
            height 0
            padding-bottom 30%
        .item-img
            width 100%
        .item-info
            padding .1rem
            .item-title
                line-height .54rem
                font-size .32rem
                ellipsis()
            .item-desc
                line-height .4rem
                color #ccc
                ellipsis()




</style>
