1. 最近使用qiank，主应用umi3.x子应用vue3.x，路由跳转返回的时候地址会自动加上undefined，导致页面白屏，可以看看这个issue, @https://github.com/umijs/qiankun/issues/2254 ，但是我的解决方案是:
```js
 router.beforeEach((to, from, next) => {
    window.history.replaceState({ ...window.history.state, current: from.path }, 0)
    next()
  })
```
暂时没发现其他问题
