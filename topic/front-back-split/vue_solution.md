## 基于vue的浏览器端渲染


### 优点

* 前后端通过接口通信，前端负责展现和交互，后端负责业务逻辑和数据<!-- .element: class="fragment" data-fragment-index="1" -->
* 切换页面时，前端只需要请求数据，不用返回除了数据之外的html、css等，性能较好<!-- .element: class="fragment" data-fragment-index="2" -->
* 前后端可以并行开发，不再互相依赖；可以单独对接口和前端交互进行测试<!-- .element: class="fragment" data-fragment-index="3" -->


### 缺点

* 不能满足 SEO 需求，SSR 方案依赖 Node.js 提供 web 服务，以及方案的有待进一步成熟<!-- .element: class="fragment" data-fragment-index="1" -->
* 到家的现状：每一个页面都是 SPA，静态资源不能充分利用；<!-- .element: class="fragment" data-fragment-index="2" -->
* 首屏加载时间过长<!-- .element: class="fragment" data-fragment-index="3" -->
* 多页面时所有页面的切换和逻辑都在前端控制，前端代码复杂度高，性能要求高，对前端人员要求较高<!-- .element: class="fragment" data-fragment-index="4" -->

