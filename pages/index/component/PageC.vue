<template>
  <view class="template-cart tn-safe-area-inset-bottom">
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

    <view class="" :style="{paddingTop: vuex_custom_bar_height + 40 + 'px'}" >
      <view class="" style="padding: 40rpx 0 280rpx 0;">
        <block v-for="(item, index) in content" :key="index">
          <view class="tn-flex tn-flex-col-top tn-margin tn-padding-xs">
            <view class="tn-flex tn-flex-col-center">
              <view class="tn-padding-right">
                <view class="tn-icon-circle tn-text-xl tn-color-gray"></view>
              </view>
              <view class="image-pic" :style="'background-image:url(' + item.mainImage + ')'" @click="tn('/productPages/details')">
                <view class="image-cart">
                </view>
              </view>
            </view>
            <view class="tn-padding-left-sm" style="width: 90%;">
              <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-lg">
                <view class="justify-content-item">
                  <text class="tn-color-black clamp-text-1">{{ item.desc }}</text>
                </view>
                <view class="justify-content-item">
                  <text class="tn-color-gray--disabled tn-icon-close"></text>
                </view>
              </view>
              <view class="tn-flex tn-flex-row-between tn-flex-col-between">
                <view class="justify-content-item tn-padding-top-xs">
                  <text class="tn-color-gray clamp-text-1 tn-text-sm">规格：金饰，纯金</text>
                </view>
              </view>
              <view class="tn-flex tn-flex-row-between tn-flex-col-between tn-padding-top-lg">
                <view class="justify-content-item tn-padding-top-xs tn-color-black">
                  <text class="clamp-text-1">￥</text>
                  <text class="clamp-text-1 tn-text-lg">{{ item.price }}</text>
                </view>
                <view class="justify-content-item" style="opacity: 0.6;">
                  <tn-number-box v-model="value" :min="1" :max="9" :disabledInput="true" backgroundColor="#FFFFFF"></tn-number-box>
                </view>
              </view>
              <view class="tn-flex tn-flex-row-between tn-flex-col-between">
                
              </view>
            </view>
          </view>
        
        </block>
        
      </view>
    </view>
    
    <view class="tabbar footerfixed" :style="{Top: vuex_custom_bar_height + 'px'}">
      <view class="tn-flex tn-flex-row-between tn-flex-col-center">
        <view class="justify-content-item tn-margin-top">
          <view class="tn-flex tn-flex-row-center tn-flex-col-center">
            <view class="tn-flex tn-flex-row-center tn-padding-right tn-padding-left">
              <text class="tn-icon-circle tn-text-xl tn-color-gray"></text> 
              <text class="tn-padding-left-xs tn-color-gray">全选</text>
            </view>
            <view class="tn-flex tn-flex-row-center tn-flex-col-center">
              <view class="tn-padding-right tn-text-ellipsis">
                <view class="tn-padding-right tn-padding-left-sm">
                  <text>总价：￥</text>
                  <text class="tn-text-lg">1,920</text>
                </view>
              </view>
            </view>
          </view>
        </view>
        <view class="justify-content-item tn-flex-row-center tn-margin-top tn-padding-right">
          <tn-button shape="round" backgroundColor="tn-bg-black" width="100%" @click="tn('/pages/payment/payment')">
            <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
              前往结算
            </text>
          </tn-button>
        </view>
      </view>
    </view>
   
    

  </view>
</template>

<script>
  export default {
    name: 'Cart',
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
      // 跳转
      tn(e) {
        // 短震动跳转
        wx.vibrateShort();
      	uni.navigateTo({
      		url: e,
      	});
      },
    }
  }
</script>

<style lang="scss" scoped>
  .template-cart{
    max-height: 100vh;
  }
  
  /* 底部安全边距 start*/
  .tn-tabbar-height {
  	min-height: 120rpx;
  	height: calc(140rpx + env(safe-area-inset-bottom) / 2);
    height: calc(140rpx + constant(safe-area-inset-bottom));
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
  
  /* 底部 start*/
  .footerfixed{
   position: fixed;
   width: 100%;
   z-index: 999;
   background-color: #F6F6F6;
   // box-shadow: 0rpx 0rpx 30rpx 0rpx rgba(0, 0, 0, 0.07);
  }
  
  .tabbar {
    align-items: center;
    min-height: 130rpx;
  	padding: 0;
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
