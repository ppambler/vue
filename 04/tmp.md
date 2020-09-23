## ★总结

## ★Q&A

1）在 JS 里边，如何拿到对象的内存地址？

问题缘由：

![问题缘由](assets/img/2020-09-23-10-36-20.png)

`tagListModel`自己维护了一个`data`状态，我们通过这个对象提供的 API 去操作这个`data`！而这个`data`也是每个模块公有的值！

➹：[请问 JavaScript 里面怎么获取某个变量的内存地址？并打印出来 - 的回答 - SegmentFault 思否](https://segmentfault.com/q/1010000015236330/a-10120000015237110)

➹：[javascript - 有没有一种方法可以在 JavaScript 中获取对象的内存地址和对象的哈希值 - IT 工具网](https://www.coder.work/article/1865903)

2）global 对象存在吗？为啥我们可以在 TS 里边，直接定义一个 Window 接口？

不存在 `global` 这个变量，但存在 `window = { global 的键值对 }` -> 可存在一个叫`Window`的构造器呀！只是我们无法 `new` 罢了！

➹：[JS/JavaScript 中的概念区分：global 对象、window 对象、document 对象](https://blog.csdn.net/chenchunlin526/article/details/78908592)

3）多个文件导入同一个模块，那么这个模块是否是一样的？

无论执行环境和实现如何，js 代码本身在 import 完成之前是不会被执行的，所以就好像在“执行”之前存在一个静态的编译期一样。

为什么题主的那一种写法会报错呢，因为在 import 完成之前，代码是不被执行的。

那么为什么代码一定要等 import 完成才会执行，是因为 import 需要时间，而如果要在代码运行的中途支持这种写法，那么脚本执行就必须被阻塞，但这样的阻塞在浏览器中会导致用户界面阻塞，所以这样的阻塞必须被“提前”，于是就形成了“import 之前代码不被执行”的操作。

实际上 es6 是支持动态 import 的，import 函数的签名是 `string->Promise`，用 Promise 就可以避免阻塞带来的问题了

➹：[多个文件 import 的相同模块里的对象，是否永远都是同一个对象？ - 知乎](https://www.zhihu.com/question/266129549)

➹：[Module 的语法 - ECMAScript 6 入门](https://es6.ruanyifeng.com/#docs/module)

➹：[深入理解 ES6 模块机制 - 前端](https://juejin.im/entry/6844903565236895758)

➹：[代码静态分析的原理是什么？ - 知乎](https://www.zhihu.com/question/28764803)

➹：[如何理解es6中的import是静态编译执行的？（一说是编译期执行的）？ - 知乎](https://www.zhihu.com/question/265631914)

4）`position: fixed` 定位的元素如何实现水平居中？

``` css
.demo {
    position:fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

➹：[position:fixed定位的元素，如何实现绝对居中，并且宽度自适应内容的宽度 - SegmentFault 思否](https://segmentfault.com/q/1010000002986876)