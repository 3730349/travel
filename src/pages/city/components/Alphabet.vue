<template>
    <ul class="list">
       <li class="item" 
       v-for="item of letters" 
       :key="item"
       :ref="item"
       @touchstart='handleTouchStart'
       @touchmove='handleTouchMove'
       @touchend='handleTouchEnd'
       @click="handleLetterClick">
       {{item}}
       </li>
    </ul>

</template>
<script>
export default {
    name: 'CityAlphabet',
    props: {
        cities: Object
    },
    computed: {
        letters () {
            const letters = []
            for(let i in this.cities) {
                letters.push(i)
            }
            return letters
        } 
    },
    data () {
        return {
                TouchStatus: false,
                startY: 0,
                timer: null

        }
    },
    updated () {
        this.startY = this.$refs['A'][0].offsetTop
    },
    methods: {
        handleLetterClick (e) {
            this.$emit('change',e.target.innerText)
        },
        handleTouchStart () {
            this.TouchStatus = true
        },
        handleTouchMove (e) {
            if(this.TouchStatus) {
                if(this.timer) {
                    clearTimeout(this.timer)
                }
                this.timer = setTimeout(() => {
                    const touchY = e.touches[0].clientY - 104;
                    const index = Math.floor((touchY - this.startY) / 19)
                    if(index >= 0 && index < this.letters.length){
                        this.$emit('change', this.letters[index])
                    }
                },16)

            }
        },
        handleTouchEnd () {
            this.TouchStatus = false
        }
    }
}
</script>
<style lang='stylus' scoped>
    @import '~reset/varibles.styl';
    .list
        display flex
        flex-direction column
        justify-content center
        position absolute
        top 1.88rem
        right 0
        bottom 0
        width .4rem
        // background red
        .item
            text-align center
            line-height .34rem
            color $bgColor




</style>
