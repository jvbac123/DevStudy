#### Vue



v-on: @

v-bind: :



#### Vue生命周期

+ 创建
  + **beforeCreate**  创建前
  + **created**  实例创建完成
  + **beforeMount**  挂载开始之前
  + **mounted**  挂载完成

+ 更新
  + **beforeUpdate**  数据更新前
  + **updated**  更新后
+ 销毁
  + **beforeDestroy**  准备死亡
  + **destroyed**  销毁











###### Vue devTools不显示

Vue 2/3版本使用的是不同的Devtools



Vue3 只能用 >=6 的版本 Chrome 商店没有 只能下载github

[Releases · vuejs/devtools (github.com)](https://github.com/vuejs/devtools/releases)



##### Vite

创建

~~~sh
使用 NPM:

$ npm init vite@latest
使用 Yarn:

$ yarn create vite
~~~



代理转发服务器

~~~json
  server:{
    host:"0.0.0.0",
    proxy:{
      '/api': {
        target:'http://127.0.0.1:2001',
        changeOrigin: true,
        rewrite: path => path.replace(/^\/api/, '')
      }
    }
  }
~~~





