<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icon" v-for="item of page" 
                :key="item.id"
                >
                    <div class="icon-img">
                        <img :src='item.ingUrl' class="icon-img-content">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>     
    </div>
</template>
<script>
export default {
    data () {
        return {
           iconList: [{
               id:"0001",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0002",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0003",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0004",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0005",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0006",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0007",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0008",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            },
            {
               id:"0009",
               ingUrl:"http://img1.tcquan.cc/images/1/2018/08/XXnABJzffzB7r5v09OkoNBj7KnNR9R.jpg",
               desc: "景点门票"
            }]
            
        }
    },
    computed: {
        pages () {
            const pages = []
            this.iconList.forEach((item,index) =>{
                const page = Math.floor(index / 8);
                if (!pages[page]) {
                    pages[page] = [];
                }
                pages[page].push(item);
            })
            return pages
        }
    }
}
</script>
<style lang="stylus" scoped>
    @import '~reset/varibles.styl';
    @import '~reset/mixins.styl';
    .icons >>> .swiper-container
        height 0
        padding-bottom 50%
    .icons 
        margin-top 0.1rem
        .icon
            position relative
            overflow hidden
            float left
            width 25%
            height 0
            padding-bottom 25%
            .icon-img
                position absolute
                top 0
                left 0
                right 0
                bottom .44rem
                box-sizing border-box
                padding 0.1rem
                .icon-img-content
                    display block
                    margin 0 auto
                    height 100%
            .icon-desc
                position absolute
                left 0
                right 0
                bottom 0
                height 0.44rem
                line-height .44rem
                color $derkTextColor
                text-align center
                font-size .26rem
                ellipsis()

            
</style>
