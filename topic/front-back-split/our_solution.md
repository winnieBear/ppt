## 平台的实践

* 基于 jello 进行定制插件开发，扬长避短
* 充分利用了jello 对 velocity 模板的语法扩充（继承、组件、重载的特性）
* 根据页面使用的组件情况，自动完成构建配置
* 舍弃原方案的渲染时，页面依赖的静态资源根据map.json动态生成，而是变成构建时自动生成,方便排查问题
* 更方便后端的接入


## 实践情况

* 到家 PC 官网，m 官网


## 使用介绍演示

* 模板的继承，重载<!-- .element: class="fragment" data-fragment-index="1" -->
* 组件<!-- .element: class="fragment" data-fragment-index="2" -->
* 根据构建条件自动对静态资源的合并，压缩，替换（css/js/imgage)<!-- .element: class="fragment" data-fragment-index="3" -->
* 根据环境自动加载对应环境(dev/test/sandbox/prod)的静态资源链接，自动切换接口环境<!-- .element: class="fragment" data-fragment-index="4" -->
* 修改完自动构建，刷新浏览器<!-- .element: class="fragment" data-fragment-index="5" -->
* 部署和上线<!-- .element: class="fragment" data-fragment-index="6" -->


### 存在的问题

* 被认为是落后的开发模式，人才吸引不够<!-- .element: class="fragment" data-fragment-index="1" -->
* 虽然大部分时间可以独立部署模板，有的需求在部署时需要跟后端一块部署，预计Q1会改变<!-- .element: class="fragment" data-fragment-index="2" -->
* 前端缺乏定位问题的能力，需要后端协助，需要多了解更多后端的知识<!-- .element: class="fragment" data-fragment-index="3" -->
* 可能存在极少数开发时没问题，测试时发现的问题，需要添加对应的配置等<!-- .element: class="fragment" data-fragment-index="4" -->

