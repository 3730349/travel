<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
        <swiper-slide v-for="item of swiperList" :key="item.id">
            <img :src="item.imgURL" class="swiper-img">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
  </div>
</template>

<script>
export default {
    name:'HomeSwiper',
    data () {
        return {
            swiperOption: {
                pagination: '.swiper-pagination'
            },
            swiperList: [
                {
                    id: '0001',
                    imgURL:'//g.search3.alicdn.com/img/i3/53936963/O1CN0121J6H6eE4VRgR6i_!!0-saturn_solar.jpg_220x220.jpg_.webp'
                },
                {
                    id: '0002',
                    imgURL:'//g.search3.alicdn.com/img/i3/53936963/O1CN0121J6H6eE4VRgR6i_!!0-saturn_solar.jpg_220x220.jpg_.webp'
                }

            ]
        }
            
    }
}

</script>

<style lang='stylus' scoped>
    .wrapper >>> .swiper-pagination-bullet-active 
        background #fff
    .wrapper
        width 100%
        overflow hidden
        height 0
        padding-bottom 100%
        background #eee
        .swiper-img 
            width 100%
</style>
