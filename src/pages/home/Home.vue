<template>
  <div>
  <div>我回来啦66666</div>
  <home-header></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icons :list="iconList"></home-icons>
  <home-recommend :list="recommendList"></home-recommend>
  <home-weekend :list="weekendList"></home-weekend>
  </div>
  
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
import { mapState } from 'vuex'
(function (doc, win) {
        var docEl = doc.documentElement,
            resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
            recalc = function () {
                var clientWidth = docEl.clientWidth;
                if (!clientWidth) return;
                if(clientWidth>=640){
                    docEl.style.fontSize = '100px';
                }else{
                    docEl.style.fontSize = 100 * (clientWidth / 640) + 'px';
                    // docEl.style.fontSize = 50 + 'px';
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
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
      return {
          lastCity: '',
          swiperList: [],
          iconList: [],
          recommendList: [],
          weekendList: []
      }
  },
  computed: {
      ...mapState(['city'])
  },
  methods: {
      getHomeInfo () {
          axios.get('/api/city.json?city='+ this.city)
            .then(this.getHomeInfoSucc),
          axios.get('/static/mock/index.json')
            .then(this.getSwiperSucc)
      },
      getHomeInfoSucc (res) {
          res = res.data;
          if(res.ret && res.data) {
              const data = res.data;
            //   this.list = data.swiperList.imgUrl;
          }
      },
      getSwiperSucc (res) {
          res = res.data;
          if(res.ret && res.data) {
              const data = res.data;
            //   this.city = data.hotCities[0].name;
              this.swiperList = data.swiperList;
              this.iconList = data.iconList;
              this.recommendList = data.recommendList;
              this.weekendList = data.weekendList;
          }
      }
  },
  mounted () {
      this.lastCity = this.city
      this.getHomeInfo()
  },
  activated () {
      if(this.lastCity !== this.city) {
          this.lastCity = this.city
          this.getHomeInfo()
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
    
</style>
