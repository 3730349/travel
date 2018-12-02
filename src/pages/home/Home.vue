<template>
  <div>
  <home-header></home-header>
  <home-swiper></home-swiper>
  <div>55555</div>
  </div>
  
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
(function (doc, win) {
        var docEl = doc.documentElement,
            resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
            recalc = function () {
                var clientWidth = docEl.clientWidth;
                if (!clientWidth) return;
                if(clientWidth>=640){
                    docEl.style.fontSize = '100px';
                }else{
                    // docEl.style.fontSize = 100 * (clientWidth / 640) + 'px';
                    docEl.style.fontSize = 50 + 'px';
                }
            };

        if (!doc.addEventListener) return;
        win.addEventListener(resizeEvt, recalc, false);
        doc.addEventListener('DOMContentLoaded', recalc, false);
    })(document, window);
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>

</style>
