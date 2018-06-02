<template>
    <div>
      <div class="search-bar">
        <van-row>
          <van-col span="3">
            <img :src="locationIcon" width="80%" alt="" class="location-icon">
          </van-col>
          <van-col span="16">
            <input class="search-input" type="text"/>
            </van-col>
          <van-col span="5">
            <van-button class="" size="mini">查找</van-button>
          </van-col>
        </van-row>
      </div>
      <!-- swiper area -->
      <div class="swiper-area">
        <van-swipe :autoplay="2000">
          <van-swipe-item v-for="(banner,index) in bannerPicArray" :key="index">
            <img v-lazy="banner.image" alt="" width="100%" />
          </van-swipe-item>
        </van-swipe>
      </div>
      <!-- type-bar -->
      <div class="type-bar">
        <div v-for="(cate,index) in category" :key="index">
          <img v-lazy="cate.image" alt="" width="100%">
          <span>{{cate.mallCategoryName}}</span>
        </div>
      </div>      
      <!--AD banner area-->
      <div class="ad-banner">
          <img v-lazy="adBanner.PICTURE_ADDRESS" width="100%">
      </div>
    </div>
</template>

<script>
import axiso from "axios";
export default {
  data() {
    return {
      msg: "shopping Mall",
      locationIcon: require("../../assets/images/location.png"),
      bannerPicArray: [ ],
      category: [],
      adBanner: ""
    };
  },

  created() {
    axiso({
      url: "https://easy-mock.com/mock/5b128ccb791ed91ba99b1143/SmileVue/index",
      method: "get"
    })
      .then(response => {
        console.log(response);
        if (response.status == 200) {
          this.category = response.data.data.category;
          this.adBanner = response.data.data.advertesPicture;
          this.bannerPicArray = response.data.data.slides
        }
      })
      .catch(error => {
        console.log(error);
      });
  }
};
</script>

<style scoped>
.search-bar {
  height: 2.2rem;
  background-color: #e5017d;
  line-height: 2.2rem;
  overflow: hidden;
}
.search-input {
  width: 100%;
  height: 1.3rem;
  border: none;
  border-bottom: 1px solid white;
  background-color: #e5017d;
  color: #fff;
}
.location-icon {
  padding-top: 0.2rem;
  padding-left: 0.3rem;
}
.swiper-area {
  clear: both;
  max-height: 15rem;
  overflow: hidden;
}
.type-bar {
  background-color: #fff;
  margin: 0 0.3rem 0.3rem 0.3rem;
  border-radius: 0.3rem;
  font-size: 14px;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
}
.type-bar div {
  padding: 0.3rem;
  font-size: 12px;
  text-align: center;
}
</style>