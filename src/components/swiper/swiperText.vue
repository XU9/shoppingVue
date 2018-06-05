
<template>
  <div >
      <swiper class="swiper" :options="swiperOption">
        <swiper-slide class="text">
            <div class="centent">
               IT之家5月27日消息 根据人民日报的报道，在黑龙江省安达市，松辽盆地大陆深部科学钻探工程即松科二井超额完成预定目标，胜利完井。据悉，这是全球首个钻穿白垩纪陆相地层的科学钻探井，标志着我们已经到达了恐龙时代。



松科二井工程首席工程师士王成善表示，松科二井完井是国际大陆科学钻探计划历程中一件大事，也是中国入地工程一件标志性事件。

王成善还表示，这是全球首次实现了对白垩纪(距今1.45亿到0.65亿年)最完整、最连续陆相地层厘米级高分辨率的精细刻画，首次重建了白垩纪陆相百万年至十万年尺度气候演化历史，发现了大规模火山爆发排放二氧化碳引发陆相气候剧烈波动的重要信息。

据悉，松科二井于2014年4月13日开钻，历时4年多时间，完钻井深7018米，成为亚洲国家实施的最深大陆科学钻井和国际大陆科学钻探计划(ICDP)成立22年来实施的最深钻井。工程取得了地质科技四项重大突破与进展。
            </div>
        </swiper-slide>
        
      </swiper>
  </div>
</template>
 
<script>
    import 'swiper/dist/css/swiper.css' 
    import { swiper, swiperSlide } from 'vue-awesome-swiper'
    export default {
        data() {
            return {
                swiperOption:{
                    direction:'vertical',
                    slidesPerView: 'auto',
                    freeMode:true,
                    mousewheel:true
                }
            }
        },
        components:{swiper,swiperSlide}
    }
</script>
 
<style scoped>
  .swiper{
      height: 300px;
      overflow: hidden;
  }
  .text{
      font-size: 18px !important;
      text-align: left;
      padding:30px;
      height: auto;
      -webkit-box-sizing: border-box;
      box-sizing: border-box;
   
  }
</style>