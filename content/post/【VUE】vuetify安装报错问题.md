---
title: "【VUE】Vuetify安装报错问题"
date: 2021-11-12T21:48:39+08:00
draft: true
---



# 在安装 vuetify 时 报错

```
ERROR  Error: You cannot call "get" on a collection with no paths. Instead, check the "length" property first to verify at least 1 path exists.
```

# 解决方案

打开main.js 文件

默认里面是

```js
import { createApp } from "vue";
import App from "./App.vue";

createApp(App).mount("#app");

```



替换为

```js
import Vue from "vue";
import App from "./App.vue";
import vuetify from "./plugins/vuetify";

new Vue({
  vuetify,
  render: (h) => h(App),
}).$mount("#app");

```

# 报错原因

## 因为当前 Vue 3.0 发布不久，vuetify 对 Vue 3.0 的语法没有做适配更新





相关链接 

Vue 3.0 使用 Vuetify中的坑 ： https://learnku.com/articles/49433

