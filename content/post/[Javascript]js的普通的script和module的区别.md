---
title: "[Javascript]js的普通的script和module的区别"
date: 2021-10-31T19:52:36+08:00
draft: true
---

# 【Javascript】   js的普通的script和module的区别

## 我们在写自己的 js 脚本时，通常是这样的

```html
<script src="./myscrpit"></script>
```

## 在我们的脚本中 再导入一些 库时 通常是这样写的

```js
import { OrbitControls } from '../lib/three.js-master/examples/jsm/controls/OrbitControls.js'
```

## 但是这样写会报错 : "Uncaught SyntaxError: Cannot use import statement outside a module"

```
Uncaught SyntaxError: Cannot use import statement outside a module
```

<img src="https://blog.clayliu.com/post/img/js/image-20211031193534064.png" style="zoom:200%;" />





# 解决办法：

## 我们在写自己的 js 脚本

```html
<script type="module" src="./myscrpit"></script>
```

## 导入一些 库时 这样写

```js
import { OrbitControls } from '../lib/three.js-master/examples/jsm/controls/OrbitControls.js'
```

## 注意：只是在我们自己写的脚本的标签的前面加上   type="module"  

# 原因：

## 加上 type="module"  告诉浏览器 应该将我们的 脚本 看做是 module 而不是 普通的 脚本来对待



# 反思：

## 为什么加上了 type="module"  就可以了呢？

## 回答：

## 普通的脚本 就是我们日常自己写的 “脚本”,

```html
<script src="./myscrpit"></script>
```

## 而加上 type="module" 之后，就是一个 包含 ES6 语法的 module,可以使用 ES6 中的 声明 （declarations）, 可以使用 `import` `export`  等等 语法

## 简而言之，加上了  type="module" 之后 才能使用ES6 语法而默认的 

```html
<script src="./myscrpit"></script>
```

## 是不包含ES6 语法的



**了解更多：**

https://stackoverflow.com/questions/39652618/classic-scripts-v-s-module-scripts-in-javascript

https://reactgo.com/cant-use-import-statement/

https://reactgo.com/node-es6-imports/
