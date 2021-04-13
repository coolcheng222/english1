# 英语作业1
[md](https://github.com/coolcheng222/english1/blob/master/%E5%BE%AE%E6%9C%BA%E7%B3%BB%E7%BB%9F.md)
# vue router笔记
## 路由匹配
动态路由匹配可以提供正则表达式作为匹配依据，以此可以根据参数内容区分不同的url
* 实例：
  * `/user/:id(\\d+)`匹配数字而`/user/:name`匹配其他内容
参数还可以匹配零级一级或多级路径
* 实例
  * `/:user+` 匹配一级或多级目录，$route.params.user表现形式为数组
  * `/:user*` 匹配零级或多级目录
  * `/:user?` 匹配零级或一级目录
多级路径匹配可以与正则共用
* 实例
  * `/:user(\\d+)+`匹配一级或多级有数字目录
## 附. 获取对应名字+参数的url路径
```js
// 给定 { path: '/:chapters*', name: 'chapters' },
router.resolve({ name: 'chapters', params: { chapters: [] } }).href
// 产生 /
router.resolve({ name: 'chapters', params: { chapters: ['a', 'b'] } }).href
// 产生 /a/b

// 给定 { path: '/:chapters+', name: 'chapters' },
router.resolve({ name: 'chapters', params: { chapters: [] } }).href
// 抛出错误，因为 `chapters` 为空 
```
