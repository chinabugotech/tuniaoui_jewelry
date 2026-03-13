<template>
  <view class="template-payment">
    <!-- 顶部自定义导航 -->
    <tn-nav-bar fixed customBack :bottomShadow="false" backgroundColor="#FFFFFF">
      <view slot="back" class='tn-custom-nav-bar__back'
        @click="goBack">
        <text class='icon tn-icon-left'></text>
      </view>
      <view class="tn-flex tn-flex-col-center tn-flex-row-center ">
        <text class="tn-text-xl tn-color-black">订单支付</text>
      </view>
    </tn-nav-bar>
    
    
    <view class="" :style="{paddingTop: vuex_custom_bar_height + 20 + 'px'}">
      
      <view class="" @click="navAddress">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-top-xs tn-padding-bottom-xs">
          <view class="justify-content-item">
            <view class="tn-flex tn-flex-col-center tn-flex-row-left">
              <view class="tn-padding tn-color-black">
                <view class="tn-padding-right-sm tn-text-bold">
                  <text class="tn-text-xl">徐吖圆</text>
                  <text class="tn-padding-left-sm tn-text-lg">183 6666 6666</text>
                </view>
                <view class="tn-padding-right tn-padding-top-xs tn-text-ellipsis tn-color-gray">
                  <text class="">广东省广州市番禺区祈福新邨129号</text>
                </view>
              </view>
            </view>
          </view>
          <view class="tn-flex justify-content-item tn-flex-row-center tn-padding-right-xs">
            <view class="tn-bg-white tn-padding-xs tn-margin-sm tn-color-black tn-round">
              <text class="tn-icon-location-fill" style="font-size: 60rpx;"></text>
            </view>
          </view>
        </view>
      </view>
      
      <block v-for="(item, index) in content" :key="index">
        <view class="tn-flex tn-flex-col-top tn-margin">
          <view class="image-pic" :style="'background-image:url(' + item.mainImage + ')'" @click="tn('')">
            <view class="image-cart">
            </view>
          </view>
          <view class="tn-padding-left" style="width: 100%;">
            <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-lg">
              <view class="justify-content-item">
                <text class="tn-color-black clamp-text-1">{{ item.desc }}</text>
              </view>
            </view>
            <view class="tn-flex tn-flex-row-between tn-flex-col-between">
              <view class="justify-content-item tn-padding-top">
                <text class="tn-color-gray clamp-text-1 tn-text-sm">规格：S码，棕色</text>
              </view>
            </view>
            <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-sm">
              <view class="justify-content-item tn-padding-top-xs">
                <text class="tn-color-gray clamp-text-1 tn-text-sm">数量：X1</text>
              </view>
              <view class="justify-content-item tn-padding-top-xs tn-color-black">
                <text class="clamp-text-1 tn-text-xs" style="padding-right: 4rpx;">￥</text>
                <text class="clamp-text-1 tn-text-lg">{{ item.price }}</text>
              </view>
            </view>
            <view class="tn-flex tn-flex-row-between tn-flex-col-between">
              
            </view>
          </view>
        </view>
      
      </block>
      
      
      <view class="tabbar footerfixed tn-bg-white">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-top-xs">
          <view class="justify-content-item tn-margin-top">
            <view class="tn-flex tn-flex-row-center tn-flex-col-center">
              <view class="tn-flex tn-flex-row-center tn-flex-col-center">
                <view class="tn-padding-right tn-padding-left tn-text-ellipsis">
                    <text class="tn-text-sm" style="padding-right: 4rpx;">￥</text>
                    <text class="tn-text-xxl tn-padding-left-xs">1,920</text>
                </view>
              </view>
            </view>
          </view>
          <view class="justify-content-item tn-flex tn-flex-row-center tn-margin-top tn-padding-right">
            <view class="tn-flex-1 justify-content-item tn-margin-right-lg tn-text-center">
              <tn-button :plain="true" backgroundColor="tn-bg-black" width="110%"  @click="tn('')">
                <text class="tn-color-black" hover-class="tn-hover" :hover-stay-time="150">
                  朋友代付
                </text>
              </tn-button>
            </view>
            <view class="tn-flex-1 justify-content-item tn-margin-right-sm tn-text-center">
              <tn-button backgroundColor="tn-bg-black" width="110%"  @click="tn('')">
                <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
                  立即支付
                </text>
              </tn-button>
            </view>
          </view>
        </view>
      </view>
      
      <view class='tn-tabbar-height'></view>
      
    </view>
  </view>
</template>

<script>
  import template_page_mixin from '@/libs/mixin/template_page_mixin.js'
  export default {
    name: 'TemplatePayment',
    mixins: [template_page_mixin],
    data(){
      return {
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
      // 收货地址
      navAddress() {
        uni.chooseAddress({
        })
      },
    }
  }
</script>

<style lang="scss" scoped>
  /* 胶囊*/
  .tn-custom-nav-bar__back {
    width: 40%;
    height: 100%;
    position: relative;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    box-sizing: border-box;
    // background-color: rgba(0, 0, 0, 0.15);
    border-radius: 1000rpx;
    // border: 1rpx solid rgba(255, 255, 255, 0.5);
    color: #000000;
    font-size: 18px;
    
    .icon {
      display: block;
      flex: 1;
      margin: auto;
      text-align: center;
    }
  }
  
  /* 底部安全边距 start*/
  .tn-tabbar-height {
  	min-height: 120rpx;
  	height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
  }
  
  /* 底部 start*/
  .footerfixed{
   position: fixed;
   width: 100%;
   bottom: 0;
   z-index: 999;
   // background-color: rgba(255,255,255,1);
   // box-shadow: 0rpx 0rpx 30rpx 0rpx rgba(0, 0, 0, 0.07);
  }
  
  .tabbar {
    align-items: center;
    min-height: 130rpx;
  	padding: 0;
  	height: calc(130rpx + env(safe-area-inset-bottom) / 2);
  	padding-bottom: calc(30rpx + env(safe-area-inset-bottom) / 2);
    padding-left: 10rpx;
    padding-right: 10rpx;
  }
 
 
  .image-cart{
    width: 200rpx;
    height: 250rpx;
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
</style>
