# 微信小程序电商平台
---
## 介绍
1. 优选平台，项目包括首页展示、商品分类、购物车、个人中心、商品详情、商品收藏、订单查询、搜索中心等页面。
2. 免费接口：[数据接口](https://www.showdoc.com.cn/128719739414963/2513235043485226)
3. 由于是个人小程序，无法发起支付请求，所以不会发起微信支付。
4. 企业微信需要对 **/pages/pay/index.js** 中 **99行** 的代码取消注释即可正常支付。（切勿支付）
##### 此项目适合大家学习使用
---
## 首页
1. 搜索是引用的自定义组件；
2. 首页图片和按钮均可正常跳转；

![](https://z3.ax1x.com/2021/09/15/4eEMqI.png)
---
## 分类
1. 搜索是引用的自定义组件；
2. 左侧和右侧高度固定，scroll-view中加上scroll-y，即可自动滚动；
3. 发起请求正常渲染即可；
4. 跳转页面时候加上cid商品分类。

![](https://z3.ax1x.com/2021/09/15/4eEmxH.png)
---
## 购物车
1. 获取本地存储数据，判断是否有购物车数据，如果有则渲染商品信息，如果没有数据则显示空购物车图片；
2. 复选框的点击改变商品checked数据，方便结算价格和数量计算。

![](https://z3.ax1x.com/2021/09/15/4eEeRe.png)
![](https://z3.ax1x.com/2021/09/15/4eEVPO.png)
---
## 个人中心
1. 判断是否登录，如果未登录显示登录按钮，登录则显示用户信息。

![](https://z3.ax1x.com/2021/09/15/4eEuMd.png)
![](https://z3.ax1x.com/2021/09/15/4eElZt.png)
---
## 商品列表
1. 搜索是引用的自定义组件；
2. 首先要在`onLoad`函数中接受列表传递的参数，用于发起请求获取商品信息；
3. 一次加载10个商品，商品上滑会继续发起下一页请求，触底后用`showToast`提示触底。
4. 上拉事件，使用`onPullDownRefresh`函数实现，还需要在json文件中配置`"enablePullDownRefresh":true`即可。

![](https://z3.ax1x.com/2021/09/15/4eEKsA.png)
---
## 商品详情
1. 点击轮播图 放大预览图片，调用小程序的api `previewImage`;
2. 点击购物车，把数组缓存到了本地，方便购物车页面调用；
3. 点击收藏，判断是否收藏，并改变颜色;
4. 点击立即购买，将地址和商品信息存储本地，并跳转支付页面；
5. 详情页面是代码则需要使用富文本标签。`rich-text`。

![](https://z3.ax1x.com/2021/09/15/4eEAIK.png)
---
## 支付页面
1. 获取本地购物车和地址数据并渲染;
2. 点击支付则发起微信支付;
3. 支付完成后跳转到订单页面。

![](https://z3.ax1x.com/2021/09/15/4eE3If.png)
---
## 订单页面
1. 发起请求，获取后台的订单数据并渲染即可。

![](https://z3.ax1x.com/2021/09/15/4eE1dP.png)
---
## 收藏页面
1. 获取数据，并渲染页面。

![](https://z3.ax1x.com/2021/09/15/4eEZGD.png)
---
## 搜索页面
1. input发生改变则向接口发起请求，并渲染页面；
2. 为了防止过快发请求，需要用定时器防抖。

![](https://z3.ax1x.com/2021/09/15/4eEGi8.png
)
