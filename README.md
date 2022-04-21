<p align="center">
    <a href="https://www.finclip.com?from=github">
    <img width="auto" src="https://www.finclip.com/mop/document/images/logo.png">
    </a>
</p>

<p align="center"> 
    <strong>FinClip ReactNative DEMO</strong></br>
<p>
<p align="center"> 
        本项目提供在 ReactNative 环境中运行小程序的 DEMO 样例
<p>

<p align="center"> 
	👉 <a href="https://www.finclip.com?from=github">https://www.finclip.com/</a> 👈
</p>

<div align="center">

<a href="#"><img src="https://img.shields.io/badge/%E4%B8%93%E5%B1%9E%E5%BC%80%E5%8F%91%E8%80%85-20000%2B-brightgreen"></a>
<a href="#"><img src="https://img.shields.io/badge/%E5%B7%B2%E4%B8%8A%E6%9E%B6%E5%B0%8F%E7%A8%8B%E5%BA%8F-6000%2B-blue"></a>
<a href="#"><img src="https://img.shields.io/badge/%E5%B7%B2%E9%9B%86%E6%88%90%E5%B0%8F%E7%A8%8B%E5%BA%8F%E5%BA%94%E7%94%A8-75%2B-yellow"></a>
<a href="#"><img src="https://img.shields.io/badge/%E5%AE%9E%E9%99%85%E8%A6%86%E7%9B%96%E7%94%A8%E6%88%B7-2500%20%E4%B8%87%2B-orange"></a>

<a href="https://www.zhihu.com/org/finchat"><img src="https://img.shields.io/badge/FinClip--lightgrey?logo=zhihu&style=social"></a>
<a href="https://www.finclip.com/blog/"><img src="https://img.shields.io/badge/FinClip%20Blog--lightgrey?logo=ghost&style=social"></a>



</div>

<p align="center">

<div align="center">

[官方网站](https://www.finclip.com/) | [示例小程序](https://www.finclip.com/#/market) | [开发文档](https://www.finclip.com/mop/document/) | [部署指南](https://www.finclip.com/mop/document/introduce/quickStart/cloud-server-deployment-guide.html) | [SDK 集成指南](https://www.finclip.com/mop/document/introduce/quickStart/intergration-guide.html) | [API 列表](https://www.finclip.com/mop/document/develop/api/overview.html) | [组件列表](https://www.finclip.com/mop/document/develop/component/overview.html) | [隐私承诺](https://www.finclip.com/mop/document/operate/safety.html)

</div>

-----
## 🤔 FinClip 是什么?

有没有**想过**，开发好的微信小程序能放在自己的 APP 里直接运行，只需要开发一次小程序，就能在不同的应用中打开它，是不是很不可思议？

有没有**试过**，在自己的 APP 中引入一个 SDK ，应用中不仅可以打开小程序，还能自定义小程序接口，修改小程序样式，是不是觉得更不可思议？

这就是 FinClip ，就是有这么多不可思议！

## 🤩 效果预览

**本项目是 FinClip 小程序在 ReactNative 工程基础上下集成及运行小程序 DEMO 演示，您可以按照下方流程测试，验证 FinClip 小程序在 ReactNative 环境下的实际效果。**

先看一下运行效果~

<p align="center">
    <a href="#">
    <img width="auto" src="./docs/mop-react-native-demo.gif">
    </a>
</p>

## ⚙️ 操作步骤
## 1. 引入插件
引入小程序引擎插件。

在 package.json 文件中引入小程序 ReactNative 插件
```objectivec
"react-native-mopsdk": "^1.0.3"
```

安装插件
```shell
$ npm install react-native-mopsdk --save
$ react-native link react-native-mopsdk
```
## 2. 初始化引擎
```objectivec
import MopSDK from 'react-native-mopsdk';
// 1. 引入 NativeModules, NativeEventEmitter
import { NativeModules, NativeEventEmitter } from 'react-native';

// 2. mop初始化
const eventEmitter = new NativeEventEmitter(NativeModules.FINMopSDK);
  MopSDK.initialize({
    appkey:
      'Ev7QHvml1UcW98Y1GaLfRz34ReffbDESaTXbCoFyKhEm0a3gam0elOOOdZ6Twpa3HkBzlvOwJ2cyhOrMVWuuGw==',
    secret: '16f2d2700453ae51',
    apiServer: 'https://api.finclip.com',
    apiPrefix: '/api/v1/mop/',
    nativeEventEmitter: eventEmitter,
    finMopSDK: NativeModules.FINMopSDK,
  }).then(res => {
    console.log('初始化成功')
  }).catch(err => {
    console.log('初始化失败')
  })

```

## 3. 打开小程序
```objectivec
MopSDK.openApplet({appId: 'xxxx'});
```


- **SDK KEY** 和 **SDK SECRET** 可以从 [FinClip](https://finclip.com/#/home)  获取，点 [这里](https://finclip.com/#/register) 注册账号；
- 进入平台后，在「应用管理」页面添加你自己的包名后，点击「复制」即可获得  key\secret\apisever 字段；
- **apiServer** 和 **apiPrefix** 是固定字段，请直接参考本 DEMO ；
- **小程序 ID** 是管理后台上架的小程序 APP ID，需要在「小程序管理」中创建并在「应用管理」中关联；
> 小程序 ID 与 微信小程序ID 不一样哦！（这里是特指 FinClip 平台的 ID ）


## 📋 接口文档
[点击这里](https://www.finclip.com/mop/document/runtime-sdk/reactNative/rn-integrate.html) 查看 React Native 快速集成文档

## 🔗 常用链接
以下内容是您在 FinClip 进行开发与体验时，常见的问题与指引信息

- [FinClip 官网](https://www.finclip.com/#/home)
- [示例小程序](https://www.finclip.com/#/market)
- [文档中心](https://www.finclip.com/mop/document/)
- [SDK 部署指南](https://www.finclip.com/mop/document/introduce/quickStart/intergration-guide.html)
- [小程序代码结构](https://www.finclip.com/mop/document/develop/guide/structure.html)
- [iOS 集成指引](https://www.finclip.com/mop/document/runtime-sdk/ios/ios-integrate.html)
- [Android 集成指引](https://www.finclip.com/mop/document/runtime-sdk/android/android-integrate.html)
- [Flutter 集成指引](https://www.finclip.com/mop/document/runtime-sdk/flutter/flutter-integrate.html)

## ☎️ 联系我们
微信扫描下面二维码，关注官方公众号 **「凡泰极客」**，获取更多精彩内容。<br>
<img width="150px" src="https://www.finclip.com/mop/document/images/ic_qr.svg">

微信扫描下面二维码，邀请进官方微信交流群（加好友备注：finclip 咨询），获取更多精彩内容。<br>
<img width="150px" src="https://finclip-homeweb-1251849568.cos.ap-guangzhou.myqcloud.com/images/ldy111.jpg">

## Stargazers
[![Stargazers repo roster for @finogeeks/finclip-react-native-demo](https://reporoster.com/stars/finogeeks/finclip-react-native-demo)](https://github.com/finogeeks/finclip-react-native-demo/stargazers)

## Forkers
[![Forkers repo roster for @finogeeks/finclip-react-native-demo](https://reporoster.com/forks/finogeeks/finclip-react-native-demo)](https://github.com/finogeeks/finclip-react-native-demo/network/members)
