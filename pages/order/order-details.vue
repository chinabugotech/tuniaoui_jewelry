<template>
  <view class="template-order">
    <!-- 顶部自定义导航 -->
    <tn-nav-bar fixed customBack :bottomShadow="false" backgroundColor="#FFFFFF">
      <view slot="back" class='tn-custom-nav-bar__back'
        @click="goBack">
        <text class='icon tn-icon-left'></text>
      </view>
      <view class="tn-flex tn-flex-col-center tn-flex-row-center ">
        <text class="tn-text-xl tn-color-black">订单详情</text>
      </view>
    </tn-nav-bar>
    
    
    <view class="" :style="{paddingTop: vuex_custom_bar_height + 20 + 'px'}">
      
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
      
      <view class="tn-bg-white" style="margin: 80rpx 30rpx 30rpx 30rpx;border-radius: 15rpx;">
        <view class="tn-flex tn-flex-row-between tn-strip-bottom-min tn-padding" v-for="(item, index) in infoList" :key="index">
          <view class="justify-content-item">
            <view class="tn-text-df">
              {{ item.title }}
            </view>
          </view>
          <view class="justify-content-item tn-text-lg tn-color-gray">
            {{ item.name }}
          </view>
        </view>
      </view>
      
      
      <view class="tabbar footerfixed tn-bg-white">
        <view class="tn-flex tn-flex-row-between tn-flex-col-center tn-padding-top-xs">
          <view class="tn-flex-2 justify-content-item tn-color-gray tn-padding-top-sm tn-margin-left">
            <button class="tn-flex tn-button--clear-style" open-type="contact" style="border-radius: 0;">
              <view class="tn-icon-service-simple" style="font-size: 52rpx;"></view>
              <view class="tn-text-center tn-padding-top-xs tn-padding-left-xs">联系商家</view>
            </button>
          </view>
          <view class="justify-content-item tn-flex tn-flex-row-center tn-margin-top tn-padding-right">
            <view class="tn-flex-1 justify-content-item tn-margin-right-lg tn-text-center">
              <tn-button :plain="true" backgroundColor="tn-bg-black" width="110%"  @click="tn('')">
                <text class="tn-color-black" hover-class="tn-hover" :hover-stay-time="150">
                  查看物流
                </text>
              </tn-button>
            </view>
            <view class="tn-flex-1 justify-content-item tn-margin-right-sm tn-text-center">
              <tn-button backgroundColor="tn-bg-black" width="110%"  @click="tn('')">
                <text class="tn-color-white" hover-class="tn-hover" :hover-stay-time="150">
                  确认收货
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
    name: 'TemplateOrder',
    mixins: [template_page_mixin],
    data(){
      return {
        content: [
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
        infoList: [
        	{
        		title: "订单编号",
        		name: "TN20241229302682",
        	},
        	{
        		title: "订单金额",
            name: "￥ 1920",
        	},
        	{
        		title: "付款金额",
            name: "￥ 1920",
        	},
          {
          	title: "支付方式",
            name: "微信支付",
          },
        	{
        		title: "下单时间",
            name: "2024-12-29 16:12:29",
        	},
          {
          	title: "支付时间",
            name: "2024-12-29 16:18:30",
          },
          {
          	title: "发货时间",
            name: "2024-12-30 09:18:08",
          },
          {
          	title: "收货姓名",
            name: "付衣衣",
          },
          {
          	title: "收货号码",
            name: "1821918888",
          },
          {
          	title: "收货地址",
            name: "广东省广州市番禺区祈福新邨129号",
          },
        ]
      }
    },
    methods: {
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
  
  /* 间隔线 start*/
  .tn-strip-bottom-min {
    width: 100%;
    border-top: 1rpx solid #F8F9FB;
  }
  
  .tn-strip-bottom {
   width: 100%;
   border-bottom: 20rpx solid rgba(241, 241, 241, 0.8);
  }
   /* 间隔线 end*/
</style>
