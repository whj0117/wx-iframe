<!--
 * @Author: wanghongjian
 * @Date: 2022-05-21 20:00:00
 * @LastEditors: wanghongjian
-->
# 问题原因
再一次需求中，需要用到iframe嵌套微信公众号页面，由于微信页面设置了响应头“frame-ancestores:self”的拦截，导致iframe不能打开
## 解决思路
核心方法就是利用cors-anywhere.herokuapp.com（最好能替换成自己的域名）这个服务段的api，将跨域请求发出去，获取到整个DOM结构，然后进行渲染，我是用的jquery的ajax进行请求。
## 使用说明
1、由于cors-anywhere.herokuapp.com被频繁滥用，导致2021年1月31日停止开发代理，原文地址[https://github.com/Rob--W/cors-anywhere/issues/301](https://github.com/Rob--W/cors-anywhere/issues/301)，有时间可以自己去看下；
2、可以通过[https://github.com/Rob--W/cors-anywhere](https://github.com/Rob--W/cors-anywhere)将cors-anywhere下载下来，在本地起服务，一篇比较不错的cors-anywhere搭建文章[https://zhuanlan.zhihu.com/p/464078121](https://zhuanlan.zhihu.com/p/464078121)，可以去看看。
