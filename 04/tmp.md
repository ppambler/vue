## ★了解更多

➹：[ts中的Record – 七月时光](https://www.leevii.com/2018/10/record-in-typescript.html)

## ★Q&A

1）`export` 一个变量 与 `export` 一个`{}`的区别？

> `export`命令用于规定模块的对外接口，`import`命令用于输入其他模块提供的功能

一个模块就是一个独立的文件。该文件内部的所有变量，外部无法获取。如果你希望外部能够读取模块内部的某个变量，就必须使用`export`关键字输出该变量。

``` js
// profile.js
export var firstName = 'Michael';
export var lastName = 'Jackson';
export var year = 1958;
```

等价姿势：

``` js
// profile.js
var firstName = 'Michael';
var lastName = 'Jackson';
var year = 1958;

// 导出列表
export { firstName, lastName, year };
```

> `import`命令接受一对大括号，里面指定要从其他模块导入的变量名。大括号里面的变量名，必须与被导入模块（`profile.js`）对外接口的名称相同。

`export`命令后面，**使用大括号指定所要输出的一组变量**-> 我很好奇这是不是在导出一个对象？其实这并不是，因为你有见过这样的语法吗？

``` js
// 重命名导出
export { variable1 as name1, variable2 as name2, …, nameN };
```

如果是一个对象的话，那就不能用 `as name1` 这样的语法了，所以 `export` 后边跟着的东西是特殊的语法

而对于「导出列表」这种姿势，外部的`import`的姿势则是 `import {xxx} from 'x.js'`

千万不要认为 `{xxx}`是一种解析赋值呀！-> 这只是样子上看上去是一样罢了！

总之，存在两种 `exports` 导出方式：

1. 命名导出（每个模块包含**任意数量**）
2. 默认导出（每个模块包含**一个**）

➹：[export - JavaScript - MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/export)

➹：[export default function 和 export function 的区别_export__开猿笔记💤](https://unnue.com/article/45)

➹：[Module 的语法 - ECMAScript 6入门](https://es6.ruanyifeng.com/#docs/module)










