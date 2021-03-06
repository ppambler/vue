### ✍️ Tangxt ⏳ 2020-09-06 🏷️ faq

# FAQ

## 1、老师，如果说 vue 只支持 IE9 及以上版本，那么是不是会影响前端技术选型？是不是你们在做开发的时候放弃 IE8 的

> 这个要**看业务**了，一般中后台系统都是不支持低版本 ie 的，vue 不支持 ie8，组件库自然也没办法支持 ie8

## 2、Vue 的响应式更新原理？

> 具体详情看「虚拟 dom 和 template」这两节课

是

> 页面加载完后，把`id='app'`下的**内容取出**，生成**虚拟树结构**，然后根据虚拟树结构生成**真实 dom 树**，然后**替换 html** 

不是

> 当页面加载完毕后 Vue 迅速查找 DOM 中的`🟡🟡🟡🟡`定界符，将定界符和其中的内容用 `app.message` 替换掉 

## 3、现在很少有公司搭建框架是用 cli 生成的吧，不都是自己按照公司需求配置一个全新的吗？

> 现在 cli 相较于以前，已经很灵活了，尤其是 cli3，我们**在 cli 之上根据公司项目特点再行自定义**，可以节省我们很多的时间 当熟悉了整个生态后，并且 **cli 满足不了项目需求的时候，再去从零去配置一个"全新"的**也是可以的

## 4、关于 `vue.config.js` 里的配置，vue-cli 版本不同对我们有影响吗？如 vue-cli2 与 vue-cli3？

> 对于配置而言，版本并不重要，你根本无须了解二者的区别！

## 5、老师，常用的 VS Code 插件？

```
Das, eslint, gitlen, jest, vetur, vscode-icons , string manipulation
```

> Das 我猜是 Dash 插件 -> 此插件可以让你在写 `xxx` API 的时候，打开 `xxx` 的使用文档！

## 6、vue 文件如何使用外部 js 呢？

>  这要看外部 js 提供的使用方式，大部分直接`npm install xxx` 就可以使用，有些可能仅支持 `script src` 方式，这本身和用不用 vue 没有关系

## 7、在使用 vue-cli 的时候，咩有热更新？

Chrome 一直报`WDS：Disconnected.`

直接修改`npm script`：

``` json
{
  "scripts": {
    "serve": "vue-cli-service serve --host localhost",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint"
  }
}
```

## 8、单文件？

单文件就是以`.vue`结尾的文件

## 9、`vue/cli` 是 `3.7.0`，但是为什么是 `v-slot:` 语法错误呢？

两种可能，第一 `v-slot`是 vue2.6 开始支持的，vue2.6 不是 `vue/cli3`， 两个是独立的，第二 `v-slot` 不支持原生标签，如 div span， 试着在 template 上使用

## 10、为什么组件注册一定要在 vue 实例创建之前呢，放在后面就不好使了，我猜测是不是跟创建过程有关啊，老师能否讲解一下？

> 不一定在实例之前，到一定要在使用之前

## 11、如果多页面用，vue 怎么写？

> 单页、多页 本身和 vue 没关系，只会涉及到打包构建并提供相应的入口文件即可。关于打包构建可以参考 cli 的文档：<https://cli.vuejs.org/zh/config/#pages>

## 12、完成功能的形式有很多种？

如元素字体的改变，你可以直接写在 `style` 属性里边，也可以写在单文件里边的`style`标签里边

如，你为了「讲作用域插槽的使用场景」，那么你可能会用了这种 `xxx` 形式来写！

## 13、请问为什么对象或数组默认值必须从一个工厂函数获取？

> 这和 `data` 必须是一个函数一样，**防止多个组件实例共享一份数据**，虽然属性默认值，我们不应该去修改它，但实际上，有些人的确去这么做了

## 14、以下两种声明有啥不一样？

``` js
{
  props: { a: 1 }
  data: function() {return { a: 1}
}
```

一个是属性，一个是状态， 属性的值来自于父组件传递，状态的值是组件自身的“值”

## 15、`:style` 的优先级是要高于 `style`的么？

实践证明是的

## 16、后续有没有基于 Vue 移动端的实战的课程？

Vue 在移动和 pc 的使用方式没有区别的，只是样式的不同，这本身和 vue 没关系

## 17、`npm run dev` 和 `npm run serve` 具体有啥区别？

`dev` 和 `serve` 只是自己起的名字，具体做什么用，是你自己在 `package.json` 的 `scripts` 字段中定义的

![脚本执行](assets/img/2020-09-06-23-47-01.png)

## 18、vue 适合做互联网主站？对 seo 和路由重定向的支持成熟吗？

只能说你想要的都有解决方案 `ssr` `phantomjs` `puppeteer`等 都可以解决`seo`

## 19、我有一定的前端基础，但是工作以来从来没有约过 angular，react 这种框架，我可以不学这两个，直接开始学习 vue 吗？

> 可以，vue 和 angular、react 是**同级的存在**

我之前一直觉得 Vue 是很牛逼的，不比 React 差，但我就是找不到说服自己的理由，直到老师说了这个 5 个字：「同级的存在」

## 20、能不能在需要的时候才从服务器获取相应的组件 vue 文件并下载后在浏览器端解析？而不是每次都打包到一起，文件大而且影响首屏渲染速度？？

可以的，可以查看文档异步组件部分，之所以课程没讲，是因为大多数项目并不需要，我们实战环节会讲到路由级别的拆包，在路由级别拆包已经足够满足我们 99% 的项目

## 21、vue-resource 和 axios 选择哪个更好呢？都一样吗？

熟悉哪个用哪个吧 从各方面数据来看 axios 更有优势些

## 22、现在 vue-cli4.0 了，ant-design-vue 兼容吗？

兼容

## 23、会有 vue-cli3.0 的讲解么？

实战使用 cli3 来创建项目 并个性化配置

## 24、老师您好，我想学习一下这个 VUE，我是先看完文档有一定的了解之后再看您的课程呢，还是说直接看您的课程就可以啊

建议先看文档，课程不可能覆盖所有的 api，就像初中高中学习一样，**有一定的预习，学习起来会更省力，收获也会更多一些**

## 25、`router–view`和`slot`区别是啥？

`Router-view` 是**全局函数式组件**，就像你自己写的一个组件注册为全局差不多，`slot` 更像是一个**占位属性**，编译时替换成 `$slots.xxx` 但说到底**都是匹配组件然后渲染组件，形式不一样而已**

## 26、函数式组件是不要求唯一根元素的吗？

使用 `render` 的确可以绕过唯一根元素的限制的，不过用 `template` 的时候，`lint` 校验过不了

## 27、`slot`的应用场景是不是可以这么理解？

比如我们在`html`里想加一个按钮，我们习惯于：

``` html
<button>添加</button>
```

这么写。

现在变成组件了，如果用`props`传递就变成了：

``` html
<Button name="添加"/>
```

如果我们用了`slot`就可以写成：

``` html
<Button>添加</Button>
```

这样啦！

> 倒是没毛病 也可以看看我写的这篇文章 <https://time.geekbang.org/column/article/87685>

看到老师这篇文章真得就理顺了很多东西！

## 28、我有个疑问：关于 `node` 版本升级问题！

> 在一个项目刚创建的时候，安装的 node 版本，在后续的话，可以任意更新吗？比如项目初期可能装的是`4.x`，我现在想升级为`10.x`。这个对整个项目会有大多影响

建议试一试，影响不大 或许会有一点兼容性问题

## 29、vue 官网写的是这么垃圾？

官网写的还可以的吧 不过作为官方的文档，更加书面一些

## 30、一个奇葩的操作：安装了`ant-design-vue`后，居然这样安装 `ant-design-vue/dist/antd.css` ？

不需要安装，况且你安装的并不是个依赖包 -> 没有 `package.json`

使用`ant-design-vue`不需要额外安装 css

