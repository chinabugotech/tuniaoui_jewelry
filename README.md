# TuniaoUI Jewelry 2.0

一个基于 `uni-app + Vue2 + Tuniao UI` 的珠宝首饰商城模板项目，整体视觉偏轻奢、深色、高级感风格，适合珠宝饰品、电商展示、品牌小程序商城等场景快速改造。

项目采用首页沉浸式视频轮播、商品双列列表、购物车结算、订单流转、个人中心等完整商城页面结构，适合作为珠宝商城前端模板或二次开发基础工程。

## 项目亮点

- 气质统一：深色系轻奢视觉，适合珠宝、首饰、礼赠类商品展示
- 首页氛围足：支持全屏视频轮播与套娃式商品展示卡片
- 商城链路完整：覆盖商品列表、商品详情、购物车、支付、订单、个人中心
- 组件化清晰：基于 `Tuniao UI` 组织页面，便于继续扩展业务模块
- 上手成本低：直接导入 `HBuilderX` 即可运行和预览

## 在线参考

- 官方模板页：[图鸟模板6-珠宝首饰](https://vue2.tuniaokj.com/theme/muse/tnmb6m.html)

## 效果预览

以下展示图参考自官方模板页，用于帮助快速了解本项目整体风格与页面表现。

<p>
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165313290-assets/web-upload/12c5f3e0-79d8-4d3a-9841-4cc64c8b00bd.jpeg" alt="官方预览图 1" height="220" />
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165308485-assets/web-upload/e5f06a3d-913f-4bb8-80f1-82b9a3ca1cc9.jpeg" alt="官方预览图 2" height="220" />
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165308986-assets/web-upload/32c35596-ae5c-4ce2-849f-b036d08f42f1.jpeg" alt="官方预览图 3" height="220" />
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165306291-assets/web-upload/c2734ea8-1ac1-4fd1-a2d6-9aa0aa890e8a.jpeg" alt="官方预览图 4" height="220" />
</p>

<p>
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165305113-assets/web-upload/aa7e2f32-fb38-431d-8c31-4da5d095d879.jpeg" alt="官方预览图 5" height="220" />
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165308003-assets/web-upload/fbfc1d4a-efcf-44bf-a03d-8881af19370c.jpeg" alt="官方预览图 6" height="220" />
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165309294-assets/web-upload/6760304a-9824-4a12-a8d5-c84d53411432.jpeg" alt="官方预览图 7" height="220" />
</p>

<p>
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165310738-assets/web-upload/6ae222c7-a3c3-4076-bb1e-c1e3ac494955.jpeg" alt="官方预览图 8" height="220" />
  <img src="https://cdn.nlark.com/yuque/0/2025/jpeg/280373/1737165310949-assets/web-upload/32b2d8ac-bb1b-48bf-a439-532652a772d2.jpeg" alt="官方预览图 9" height="220" />
</p>

## 页面结构

### 主导航页面

- `pages/index/index.vue`：主容器页，自定义底部 Tab，承载四个主分页面
- `pages/index/component/PageA.vue`：品牌首页，含视频轮播、主推商品、沉浸式展示
- `pages/index/component/PageB.vue`：商品列表，双列商品卡片 + 分类切换
- `pages/index/component/PageC.vue`：购物车页面，支持数量调整与结算入口
- `pages/index/component/PageD.vue`：个人中心，包含订单、会员、客服、反馈等入口

### 子页面

- `pages/details/details.vue`：商品详情页
- `pages/payment/payment.vue`：订单支付页
- `pages/order/order.vue`：订单列表页
- `pages/order/order-details.vue`：订单详情页

## 技术栈

- `uni-app`
- `Vue 2`
- `Tuniao UI`
- `SCSS`
- 微信小程序页面风格与交互写法

## 快速开始

### 1. 导入项目

使用 `HBuilderX` 打开项目根目录：

```bash
tuniaoui_jewelry-2.0.0
```

### 2. 运行项目

在 `HBuilderX` 中选择：

- 运行到微信开发者工具
- 运行到浏览器
- 运行到手机或模拟器

### 3. 基础说明

- 项目首页入口为 `pages/index/index.vue`
- 页面配置位于 `pages.json`
- 全局样式位于 `uni.scss`
- UI 组件位于 `tuniao-ui/`
- 当前仓库内大部分商品、订单、个人信息均为演示数据
- `manifest.json` 中已包含微信小程序 `appid` 与 `chooseAddress` 等配置，正式使用前建议自行替换和校验

## 适用场景

- 珠宝首饰商城小程序
- 轻奢礼品类电商
- 品牌珠宝展示项目
- 节日礼赠类商品商城
- 需要快速搭建高质感商城前端的 uni-app 项目

## 开发建议

- 若用于正式项目，建议先替换商品图片、品牌文案、价格、昵称、手机号与订单示例数据
- 页面中使用了较多远程图片和视频资源，如需离线部署，建议迁移为自有静态资源
- `chooseAddress`、`open-type="contact"`、`open-type="share"`、`wx.vibrateShort` 等能力需要按小程序环境分别验证

## 致谢

本项目基于 `Tuniao UI` 生态模板整理，页面风格与展示图参考图鸟官方模板页。
