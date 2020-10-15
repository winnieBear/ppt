# 移动端疑难问题调试
___

## 相关工具
- vconsole 修改过的vconsole版本，
  - 使用时不用new 一个实例，只需要引入js即可
  - 当页面有错误或异常发生时，自动hook window.onerror，能把错误信息爆出来，展示在vconsole界面

  线上地址引用地址：//static.daojia.com/assets/other/test/vconsole.min.js


## 方案1【推荐】
自己本机安装[inject_vconsole](http://git.daojia-inc.com/felib/inject_vconsole)按照文档操作

## 方法2：spy-debugger
### 方案介绍
  通过spy-debugger工具（https://github.com/wuchangming/spy-debugger）在本地电脑上调试手机上页面，spy-debugger工具封装了weinre和anyproxy在一起

### 使用方法
第一步：手机和PC保持在同一网络下（比如同时连到一个Wi-Fi下）

第二步：命令行输入spy-debugger，按命令行提示用浏览器打开相应地址。

第三步：设置手机的HTTP代理，代理IP地址设置为PC的IP地址，端口为spy-debugger的启动端口(默认端口：9888)。

Android设置代理步骤：设置 - WLAN - 长按选中网络 - 修改网络 - 高级 - 代理设置 - 手动
iOS设置代理步骤：设置 - 无线局域网 - 选中网络 - HTTP代理手动
第四步：手机安装证书。注：手机必须先设置完代理后再通过(非微信)手机浏览器访问http://s.xxx 或(二维码)安装证书（手机首次调试需要安装证书，已安装了证书的手机无需重复安装)。问题：iOS 10.3.1以上版本证书安装问题

第五步：用手机浏览器访问你要调试的页面即可。

## 方法3：使用平台测试服务器搭建的代理服务器进行调试【内网使用】

平台代理服务器做的事情
1. 所有经过转发的html里面的js文件会添加"crossorigin="anonymous" " 属性**
2. 所有经过转发的js文件会添加CORS响应头
3. 能访问 http://fedev.djtest.cn:8002/ 查看 app 所有请求

### 使用方法
1. 终端（电脑或手机）切换到有线网或 58-Office（重要）
2. 在终端上设置代理：https://static.daojia.com/assets/other/test/djfe.pac

iOS 设置方法


安卓设置方法

### 如果要抓https，需要安装 CA 证书
安装方法：访问 http://fedev.djtest.cn:8002/ 页面上进行安装 CA 证书（HTTPS 协议适用）

