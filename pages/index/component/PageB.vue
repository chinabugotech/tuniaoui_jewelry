<template>
  <view class="pagesA tn-safe-area-inset-bottom">

    <!-- 顶部自定义导航 -->
    <tn-nav-bar :isBack="false" :bottomShadow="false" backgroundColor="#F6F6F6">
      <view class="custom-nav tn-flex tn-flex-col-center tn-flex-row-left">
        <view class="custom-nav__logo" @click="tn('')">
          <view class="tn-icon-starry tn-color-black"></view>
        </view>
        <view class="tn-flex-col-center tn-flex-row-center tn-text-lg" style="margin-left: 25vw;">
          <text class="tn-text-xxl tn-color-black">TN Fashion</text>
        </view>
      </view>
    </tn-nav-bar>

    <view class="tn-margin-bottom-xl" :style="{paddingTop: vuex_custom_bar_height + 20 + 'px'}">
      
      <!-- 简单搜索框 -->
      <!-- <view class="search-fixed">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-margin-left tn-margin-right">
          
          <view class="justify-content-item align-content-item" style="width: 100vw;">
            <view class="tn-flex tn-flex-col-center tn-bg-white" style="border-radius: 20rpx;padding: 20rpx 20rpx 20rpx 30rpx;width: 96%;">
              <text class="tn-icon-search justify-content-item tn-padding-right-xs tn-text-lg leaf-color"></text>
              <input class="justify-content-item" placeholder="丑猫文学" name="input" placeholder-style="color:#838383" style="width: 100%;color: #0E2D6D;"></input>
            </view>
          </view>
          
          <view class="align-content-item">
            <view class="justify-content-item tn-text-center" style="border-radius: 20rpx;overflow: hidden;">
              <tn-button backgroundColor="#0F0F0F" padding="42rpx 20rpx" width="90rpx" @tap="">
                <text class="tn-color-white tn-icon-starry tn-text-xl"></text>
              </tn-button>
            </view>
          </view>
          
        </view>
      </view> -->
      
      <!-- 滚动搜索框-->
      <view class="search-fixed">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-margin-left tn-margin-right">
          <view class="tn-bg-white" style="color: #838383;border-radius: 20rpx;padding: 8rpx;width: 83%;" @click="tn('../search/search')">
            <tn-notice-bar :list="searlist" mode="vertical" leftIconName="search" :duration="6000"></tn-notice-bar>
          </view>
          <view class="">
            <view class="tn-text-center" style="border-radius: 20rpx;overflow: hidden;">
              <tn-button backgroundColor="#0F0F0F" padding="42rpx 20rpx" width="90rpx" @tap="">
                <text class="tn-color-white tn-icon-buy-fill" style="font-size: 50rpx;"></text>
              </tn-button>
            </view>
          </view>
        </view>
      </view>
      
      <!-- tabs导航 -->
      <view class="" style="width: 100vw;">
        <!-- <tn-sticky :offsetTop="0" :customNavHeight="vuex_custom_bar_height"> -->
          <view class="tn-padding-top tn-padding-bottom tn-margin-top-lg" style="background-color: #F6F6F6;">
            <tn-tabs :list="fixedList" :current="current" :isScroll="false" barHeight="6" barWidth="28" :showBar="false"
              :activeItemStyle="activeItemStyle" :inactiveItemStyle="inactiveItemStyle" :barStyle="barStyle" inactiveColor="#1E1E1E" activeColor="#F6F6F6" :bold="false" :fontSize="26" :badgeOffset="[10, 30]"
              @change="tabChange" backgroundColor="#F6F6F6" :height="74"></tn-tabs>
          </view>
        <!-- </tn-sticky> -->
      </view>


      <view class="" v-if="current==0">
        
        <!-- 简约商品 start-->
        <view class="tn-flex tn-flex-wrap" style="margin: 30rpx 10rpx 30rpx 10rpx;">
          <block v-for="(item, index) in content" :key="index">
            <view class="" style="width: 50%;" @click="tn('../details/details')">
              <view class="tn-product-content__wrap tn-padding-bottom-lg">
                <view class="image-pic" :style="'background-image:url(' + item.mainImage + ')'">
                  <view class="image-product">
                  </view>
                </view>
                
                <view class="tn-product-content__label tn-text-justify tn-padding-top-sm tn-padding-bottom-xs">
                  <text class="tn-product-content__label__desc tn-color-gray clamp-text-1">{{ item.desc }}</text>  
                </view>
                
                <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-bottom-sm tn-padding-top-xs">
                  <view class="justify-content-item tn-flex tn-flex-col-center" style="margin-left: -6rpx;">
                    <text class="tn-text-sm" style="padding-right: 2rpx;">￥</text>
                    <text class="tn-padding-right-sm tn-text-xl ">{{ item.price }}</text>
                    <!-- <text class="tn-color-gray tn-text-sm"> 66 人购买</text> -->
                  </view>
                  <view class="justify-content-item tn-flex tn-flex-col-center">
                    <!-- <text class="tn-color-gray tn-text-sm"> {{ item.number }} 人购买</text> -->
                    <tn-button size="sm" shape="icon" backgroundColor="#FFFFFF" fontColor="#000000" margin="10rpx">
                      <text class="tn-icon-like-fill tn-text-lg"></text>
                    </tn-button>
                  </view>
                </view>
              </view>
            </view>
          </block>
        </view>
        <!-- 简约商品 end-->
        
      </view>

      <view class="" v-if="current==1">

        <view class="" style="padding: 3vh 20rpx;opacity: 0.6;">
          <view class="tn-text-center" style="font-size: 260rpx;padding-top: 30rpx;">
            <text class="tn-icon-wea-wind tn-color-gray--disabled"></text>
          </view>
          <view class="tn-color-gray tn-text-center tn-text-lg">商品被风吹跑了，嘤</view>
        </view>

      </view>


      <view class="" v-if="current==2">

        <view class="" style="padding: 3vh 20rpx;opacity: 0.6;">
          <view class="tn-text-center" style="font-size: 260rpx;padding-top: 30rpx;">
            <text class="tn-icon-wea-wind tn-color-gray--disabled"></text>
          </view>
          <view class="tn-color-gray tn-text-center tn-text-lg">商品被风吹跑了，嘤嘤嘤</view>
        </view>

      </view>
      
      <view class="" v-if="current==3">
      
        <view class="" style="padding: 3vh 20rpx;opacity: 0.6;">
          <view class="tn-text-center" style="font-size: 260rpx;padding-top: 30rpx;">
            <text class="tn-icon-wea-wind tn-color-gray--disabled"></text>
          </view>
          <view class="tn-color-gray tn-text-center tn-text-lg">商品被风吹跑了，嘤嘤嘤嘤嘤嘤</view>
        </view>
      
      </view>

    </view>

    <view class='tn-tabbar-height'></view>
    <!-- <view class="bg-tabbar-shadow"></view> -->
  </view>
</template>

<script>
  export default {
    name: 'PageA',
    data() {
      return {
        /* 搜索*/
        searlist: [
          '搜索 红宝石耳环',
          '搜索 蓝宝石项链',
          '搜索 紫宝石戒指'
        ],
        
        /* showBar为true，就显示出来这个了*/
        barStyle: {
          borderRadius: '100rpx',
          backgroundColor: '#0F0F0F'
        },
        activeItemStyle: {
          borderRadius: '20rpx',
          // border: "1rpx solid #1D1F24",
          backgroundColor: '#1D1F24',
          margin: "0 30rpx"
        },
        inactiveItemStyle: {
          borderRadius: '20rpx',
          // border: "1rpx solid #1D1F24",
          backgroundColor: '#1D1F2400',
          margin: "0 30rpx"
        },
        current: 0,
        fixedList: [
          {name: '全部'},
          {name: '黄金'},
          {name: '钻石'},
          {name: '铂金'}
        ],
        
        content: [
          {
            price: '29.00',
            number: '19',
            desc: '简约戒指',
            mainImage: 'https://cdn.nlark.com/yuque/0/2024/jpeg/280373/1732377480895-assets/web-upload/ea5c1355-c1c6-4166-82f6-d76069442ffd.jpeg',
          },
          {
            price: '69.00',
            number: '22',
            desc: '简约戒指',
            mainImage: 'https://cdn.nlark.com/yuque/0/2024/jpeg/280373/1732377877636-assets/web-upload/679e726a-f17f-4631-b953-f784d6331b00.jpeg',
          },
          {
            price: '79.00',
            number: '6',
            desc: '项链&戒指',
            mainImage: 'https://cdn.nlark.com/yuque/0/2024/jpeg/280373/1732376431261-assets/web-upload/1d8b2f90-c1ba-4306-96a7-19f8e87cf942.jpeg',
          },
          {
            price: '59.00',
            number: '18',
            desc: '简约戒指',
            mainImage: 'https://cdn.nlark.com/yuque/0/2024/jpeg/280373/1732376880366-assets/web-upload/e7054122-476e-405e-9244-f61d2d47cac2.jpeg',
          },
          {
            price: '59.00',
            number: '2',
            desc: '那只猪不见了吗',
            mainImage: 'https://cdn.nlark.com/yuque/0/2024/jpeg/280373/1732378045477-assets/web-upload/0a358702-a67b-4769-9f91-eef4e55cd0ef.jpeg',
          },
          {
            price: '88.00',
            number: '16',
            desc: '那只猪不见了吖',
            mainImage: 'https://cdn.nlark.com/yuque/0/2024/jpeg/280373/1732376431515-assets/web-upload/4fc278a7-a84c-47dd-aac2-d91ceb8c29c2.jpeg',
          },

        ],
      }
    },

    methods: {
      // tab选项卡切换
      tabChange(index) {
        this.current = index
      },
      // 跳转
      tn(e) {
        uni.navigateTo({
          url: e,
        });
      },
    }
  }
</script>


<style lang="scss" scoped>
  .pagesA {
    max-height: 100vh;
  }

  /* 底部安全边距 start*/
  .tn-tabbar-height {
    min-height: 60rpx;
    height: calc(80rpx + env(safe-area-inset-bottom) / 2);
    height: calc(80rpx + constant(safe-area-inset-bottom));
  }

  /* 底部tabbar假阴影 start*/
  .bg-tabbar-shadow {
    // background-image: repeating-linear-gradient(to top, rgba(0,0,0,0.1) 10rpx, rgba(255,255,255,0) , rgba(255,255,255,0));
    box-shadow: 0rpx 0rpx 220rpx 0rpx rgba(0, 0, 0, 0.55);
    position: fixed;
    bottom: -100rpx;
    height: 100rpx;
    width: 100vw;
    z-index: 1;
  }

  /* 自定义导航栏内容 start */
  .custom-nav {
    height: 100%;

    &__logo {
      margin: auto 5rpx;
      font-size: 50rpx;
      margin-right: 10rpx;
      margin-left: 30rpx;
      flex-basis: 5%;
    }
  }

  /* 自定义导航栏内容 end */
  .leaf-color{
    color: #1E1E1E;
  }
  
  /* 搜索 */
  .search-fixed{
    position: relative;
    width: 100%;
  }

  /* 商家商品 start*/
  .tn-product-content {
    &__wrap {
      // box-shadow: 0rpx 0rpx 50rpx 0rpx rgba(0, 0, 0, 0.07);
      // border-radius: 20rpx;
      margin: 20rpx;
    }
    
    &__info {
      &__btn {
        margin-right: -12rpx;
        opacity: 0.5;
      }
    }
    
    &__label {
      
      &__desc {
        line-height: 35rpx;
      }
    }
  }
  
  .image-product{
    padding: 220rpx 0rpx;
    font-size: 16rpx;
    font-weight: 300;
    position: relative;
  }
  .image-pic{
    background-size: cover;
    background-repeat:no-repeat;
    // background-attachment:fixed;
    background-position:center;
    border-radius: 15rpx;
  }
  
  /* 商家商品 end*/
  
  /* 文字截取*/
  .clamp-text-1 {
    -webkit-line-clamp: 1;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    text-overflow: ellipsis;
    overflow: hidden;
  }
  
  .clamp-text-2 {
    -webkit-line-clamp: 2;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    text-overflow: ellipsis;
    overflow: hidden;
  }
  
</style>