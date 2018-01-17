## 基于 FIS3 的 jello 方案


### 优点

* 前后端通过数据约定，前端写 Velocity 模板，负责展现和交互，后端负责业务逻辑和数据<!-- .element: class="fragment" data-fragment-index="1" -->
* 前后端约定好数据之后，可以并行开发，不再互相依赖；可以单独对接口和前端交互进行测试<!-- .element: class="fragment" data-fragment-index="2" -->
* 支持 SEO<!-- .element: class="fragment" data-fragment-index="3" -->
* 页面是服务端渲染，前端可以控制首屏输出的内容，性能较好<!-- .element: class="fragment" data-fragment-index="4" -->


### 缺点

* jello 本身基本不再维护，需要自己熟悉 FIS3 的逻辑，自己能修改<!-- .element: class="fragment" data-fragment-index="1" -->
* jello 前端构建配置繁琐，一个模块只能打包到一个包里<!-- .element: class="fragment" data-fragment-index="2" -->
* 服务端渲染页面依赖的静态资源是动态生成，不便于定位问题<!-- .element: class="fragment" data-fragment-index="3" -->
* 服务端渲染模板，增加了服务器的负担，同时增加了网络传输的html部分<!-- .element: class="fragment" data-fragment-index="4" -->
* 被认为是落后的开发模式,难以吸引人才<!-- .element: class="fragment" data-fragment-index="5" -->
