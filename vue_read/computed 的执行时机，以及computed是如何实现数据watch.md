## computed 的执行时机，以及computed是如何实现数据watch

在工作中，想在vue computed使用箭头函数，发现执行computed的时候this指向的不是当前的vue实例，查看vue文档的时候发现可以将当前vue实例vm作为参数传入到computed计算属性中来使用箭头函数。

```javascript
computed: {
    test: vm => vm.somedata * 2
}
```

那么computed的执行时机是什么时候，如何通过this.xx能访问到，computed和data的数据双向绑定，watch的监听有无却别。