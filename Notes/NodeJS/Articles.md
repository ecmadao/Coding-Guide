<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Articles](#articles)
  - [Node.js](#nodejs)
    - [模块](#%E6%A8%A1%E5%9D%97)
    - [进程/线程](#%E8%BF%9B%E7%A8%8B%E7%BA%BF%E7%A8%8B)
    - [事件循环](#%E4%BA%8B%E4%BB%B6%E5%BE%AA%E7%8E%AF)
    - [**V8**](#v8)
    - [其他](#%E5%85%B6%E4%BB%96)
  - [JavaScript](#javascript)
    - [基础](#%E5%9F%BA%E7%A1%80)
    - [**How JavaScript works**](#how-javascript-works)
    - [Promise](#promise)
    - [前端](#%E5%89%8D%E7%AB%AF)
    - [React](#react)
    - [其他](#%E5%85%B6%E4%BB%96-1)
    - [扩展阅读](#%E6%89%A9%E5%B1%95%E9%98%85%E8%AF%BB)
  - [Redis](#redis)
    - [知识点](#%E7%9F%A5%E8%AF%86%E7%82%B9)
    - [其他](#%E5%85%B6%E4%BB%96-2)
  - [计算机](#%E8%AE%A1%E7%AE%97%E6%9C%BA)
  - [计算机网络](#%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C)
    - [TCP/UDP](#tcpudp)
    - [扩展阅读](#%E6%89%A9%E5%B1%95%E9%98%85%E8%AF%BB-1)
    - [HTTPS](#https)
    - [SSH](#ssh)
    - [DNS/CDN、代理](#dnscdn%E4%BB%A3%E7%90%86)
    - [网络攻击](#%E7%BD%91%E7%BB%9C%E6%94%BB%E5%87%BB)
  - [算法和数据结构](#%E7%AE%97%E6%B3%95%E5%92%8C%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84)
    - [算法](#%E7%AE%97%E6%B3%95)
    - [难点](#%E9%9A%BE%E7%82%B9)
    - [数据结构](#%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84)
  - [架构](#%E6%9E%B6%E6%9E%84)
    - [消息队列](#%E6%B6%88%E6%81%AF%E9%98%9F%E5%88%97)
    - [微服务](#%E5%BE%AE%E6%9C%8D%E5%8A%A1)
    - [稳定性](#%E7%A8%B3%E5%AE%9A%E6%80%A7)
  - [Linux](#linux)
  - [其他](#%E5%85%B6%E4%BB%96-3)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Articles

### Node.js

#### 模块

- [深入学习 Node.js Module](https://semlinker.com/node-module/)
- [Node.js 中的循环依赖](https://cnodejs.org/topic/567104f61d2912ce2a35aa88)
- [浅析 NodeJs 的几种文件路径](https://github.com/imsobear/blog/issues/48)
- [Node.js module.exports vs. exports](https://www.freecodecamp.org/news/node-js-module-exports-vs-exports-ec7e254d63ac/)
- [module.exports vs exports in Node.js](https://stackoverflow.com/questions/7137397/module-exports-vs-exports-in-node-js)

> require vs import

- [彻底搞清楚 javascript 中的 require、import 和 export](http://meiminjun.github.io/import%E5%92%8Cexport%E7%AC%94%E8%AE%B0/)
- [Using Node.js require vs. ES6 import/export](https://stackoverflow.com/questions/31354559/using-node-js-require-vs-es6-import-export)
- [The difference between “require(x)” and import x](https://stackoverflow.com/questions/46677752/the-difference-between-requirex-and-import-x)

- CommonJS 模块输出的是一个值的拷贝，ES6 模块输出的是值的引用
- CommonJS 模块是运行时加载，ES6 模块是编译时加载输出接口

> export vs export default

- [深入解析 ES Module（二）：彻底禁用 default export](https://zhuanlan.zhihu.com/p/97335917)
- [require 和 import 的区别](https://segmentfault.com/a/1190000021911869)

#### 进程/线程

- [浅析 Node 进程与线程](https://juejin.im/post/5e0728ce518825122b0f99f2)
- [NodeJS 充分利用多核 CPU 以及它的稳定性](https://segmentfault.com/a/1190000007343993)
- [当我们谈论 cluster 时我们在谈论什么](https://github.com/hustxiaoc/node.js/issues/11)
- [NodeJS 多进程](https://segmentfault.com/a/1190000004621734)
- [Node.js 软肋之 CPU 密集型任务](https://www.infoq.cn/article/nodejs-weakness-cpu-intensive-tasks/)
- [[转] Node.js 的线程和进程详解](https://github.com/xiongwilee/blog/issues/9)

#### 事件循环

事件循环/任务调度

- [The JavaScript Event Loop: Explained](https://blog.carbonfive.com/2013/10/27/the-javascript-event-loop-explained/)
- [Concurrency model and the event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)
- [【译】【Node.js at Scale】理解 Node.js 中的事件循环](./Node.js-at-Scale/)
- [Tasks, microtasks, queues and schedules](https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/)
- [微任务、宏任务与 Event-Loop](https://juejin.im/post/5b73d7a6518825610072b42b)
- [async await 和 promise 微任务执行顺序问题](https://segmentfault.com/q/1010000016147496)

setTimeout 问题

- [Difference between setTimeout(fn, 0) and setTimeout(fn, 1)?](https://stackoverflow.com/questions/8341803/difference-between-settimeoutfn-0-and-settimeoutfn-1)
- [Why is setTimeout(fn, 0) sometimes useful?](https://stackoverflow.com/questions/779379/why-is-settimeoutfn-0-sometimes-useful)

```javascript
/*
 * 宏任务：
 * 1. I/O
 * 2. setTimeout/setInterval/setImmediate
 * 3. requestAnimationFrame
 *
 * 微任务：
 * 1. process.nextTick
 * 2. Promise.then/.catch/.finally
 */

// 注意，new Promise 在实例化的过程中所执行的代码都是同步进行的，而 then 中注册的回调才是异步执行的
// async 函数在 await 之前的代码都是同步执行的，可以理解为 await 之前的代码属于 new Promise 时传入的代码，await 之后的所有代码都是在 Promise.then 中的回调
```

```javascript
setTimeout(() => {
    console.log(1)
}, 0)

new Promise((resolve) => {
    console.log(2)
    for (let i = 0; i < 100; i += 1) {
        if (i === 88) resolve()
    }
    console.log(3)
}).then(() => {
    console.log(4)
})
console.log(5)
// 2 3 5 4 1
```

#### **V8**

- [Speeding up spread elements](https://v8.dev/blog/spread-elements)
- [Fast async](https://v8.dev/blog/fast-async)
- [V8 引擎的垃圾回收策略](https://www.cnblogs.com/onepixel/p/7422820.html)
- [【译】【Node.js at Scale】Node.js 的垃圾回收机制](./Node.js-at-Scale/)
- [4 类 JavaScript 内存泄漏及如何避免](https://jinlong.github.io/2016/05/01/4-Types-of-Memory-Leaks-in-JavaScript-and-How-to-Get-Rid-Of-Them/)

#### 其他

- [Node.js Interview Questions and Answers !?](https://blog.risingstack.com/node-js-interview-questions-and-answers-2017/)
- [深入学习 Node.js EventEmitter](https://semlinker.com/node-event-emitter/)
- [深入理解 Node.js：核心思想与源码分析](https://github.com/yjhjstz/deep-into-node)

### JavaScript

- [The Modern JavaScript Tutorial](https://javascript.info/)
- [Getting creative with the Console API!](https://areknawo.com/getting-creative-with-the-console-api/)

#### 基础

> 数据类型，原型/原型链

- [**细说 JavaScript 七种数据类型**](https://www.cnblogs.com/onepixel/p/5140944.html)
- [判断 JS 数据类型的四种方法](https://www.cnblogs.com/onepixel/p/5126046.html)
- [JavaScript 中的四舍五入](https://www.cnblogs.com/onepixel/p/5141566.html)
- [**认识原型对象和原型链**](https://www.cnblogs.com/onepixel/p/5024903.html)
- [**函数作用域和作用域链**](https://www.cnblogs.com/onepixel/p/5036369.html)
- [你不知道的 JavaScript](../JavaScript/你不知道的JavaScript)
- [JavaScript 浮点数陷阱及解法](https://github.com/camsong/blog/issues/9)
- [不要再问我 this 的指向问题了](https://segmentfault.com/a/1190000015438195)

> 原型/原型链

JS 中可分为普通对象`Object`和函数对象`Function`。通过`new Function`产生的对象、声明的函数是函数对象，其他对象都是普通对象

`prototype`即原型对象，它记录着对象的一些属性和方法。
`prototype`对于父对象本身是不可见的，但子类可以完全访问。当通过`new`操作符创建新对象的时候，通常会把父类的`prototype`赋值给新对象的`__proto__`属性，子类就可以调用到继承的属性或方法。
原型链的形成真正是靠`__proto__`而非`prototype`，当 JS 引擎执行对象的方法时，先查找对象本身是否存在该方法，如果不存在，会在原型链上查找，但不会查找自身的`prototype`

```javascript
function func() {}
func.prototype.foo = 'foo'
console.log(func.foo) // undefined

const f = new func()
console.log(f.foo) // foo
```

向上追溯原型链：

1. `f.__proto__` -> `func.prototype`
2. `func.prototype.__proto__` -> `Object.prototype`
3. `Object.prototype.__proto__` -> `null`

> 提升

```javascript
// 函数声明会被提升
console.log(a) // ƒ a() { console.log('1') }
a() // 1
function a() { console.log('1') }
var a = function() { console.log('2' )}
console.log(a) // ƒ () { console.log('2' )}
```

```javascript
// 但函数表达式不会被提升
console.log(a) //  undefined
a() // TypeError
var a = function() { console.log('2' )}
console.log(a) // ƒ () { console.log('2' )}
```

```javascript
var a = function() { this.b = 1 }

a.prototype.b = 9

var c = new a()
var b = 2
a()

console.log(b)
console.log(c.b)
```

> Map/WeakMap, Set/WeakSet

- [Difference between Map and WeakMap in JavaScript](https://www.mattzeunert.com/2017/01/31/weak-maps.html)
- [What are the actual uses of ES6 WeakMap?](https://stackoverflow.com/questions/29413222/what-are-the-actual-uses-of-es6-weakmap)
- [带键的集合](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Keyed_collections)

> 判断操作

- [详解 undefined 与 null 的区别](https://www.cnblogs.com/onepixel/p/7337248.html)
- [Why `null >= 0 && null <= 0` but not `null == 0`?](https://stackoverflow.com/questions/2910495/why-null-0-null-0-but-not-null-0)
- [JavaScript 中的相等性判断](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Equality_comparisons_and_sameness)

#### **How JavaScript works**

1. [How JavaScript works: An overview of the engine, the runtime, and the call stack](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf)
2. [How JavaScript works: Inside the V8 engine + 5 tips on how to write optimized code](https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e)
3. [How JavaScript works: Memory management + how to handle 4 common memory leaks](https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec)
4. [How JavaScript works: Event loop and the rise of Async programming + 5 ways to better coding with async/await](https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5)
5. [How JavaScript works: Storage engines + how to choose the proper storage API](https://blog.sessionstack.com/how-javascript-works-storage-engines-how-to-choose-the-proper-storage-api-da50879ef576)

#### Promise

- [JavaScript Promise 迷你书（中文版）](http://liubin.org/promises-book/)
- [大白话讲解 Promise](https://www.cnblogs.com/lvdabao/p/es6-promise-1.html)
- [How do Promises Work?](https://robotlolita.me/articles/2015/how-do-promises-work/)
- [你真的完全掌握了 Promise 么](https://juejin.im/post/5af29a62f265da0b8f628973)

```javascript
/*
 * Some fact:
 * 1. 调用 resolve 或 reject 并不会终结 Promise 的参数函数的执行
 * 2. Promise 在 resolve 语句后面，再抛出错误，不会被捕获，等于没有抛出。因为 Promise 的状态一旦改变，就永久保持该状态，不会再变了
 * 3. new Promise 在实例化的过程中所执行的代码都是同步进行的，而 then 中注册的回调才是异步执行的
 * 4. async functions always return promises
 */
```

#### 前端

- [前端高性能动画最佳实践](https://mp.weixin.qq.com/s?__biz=MjM5Njc0MjIwMA==&mid=401923510&idx=1&sn=daddf02e41981b5fc7d3eb62d9c3d891&scene=0#wechat_redirect)
- [前端工程与性能优化](https://github.com/fouber/blog/issues/3)
- Cookie/Session
  - [cookie 和 session 到底是什么](https://mp.weixin.qq.com/s/lEAFW9ZSiqHJOfMnznPPHA)
  - [Cookie/Session 的机制与安全](https://harttle.land/2015/08/10/cookie-session.html)
  - [傻傻分不清之 Cookie、Session、Token、JWT](https://juejin.cn/post/6844904034181070861)
  - [详说 Cookie, LocalStorage 与 SessionStorage](https://jerryzou.com/posts/cookie-and-web-storage/)
- 事件冒泡 和 事件捕获
  - [你真的理解 事件冒泡 和 事件捕获 吗？](https://juejin.cn/post/6844903834075021326)
  - [你真的理解事件冒泡和事件捕获吗？](https://segmentfault.com/a/1190000012729080)
- 跨域问题
  - [浏览器的同源策略](https://developer.mozilla.org/zh-CN/docs/Web/Security/Same-origin_policy)
  - [**不要再问我跨域的问题了**](https://segmentfault.com/a/1190000015597029)
  - [前端常见跨域解决方案（全）](https://segmentfault.com/a/1190000011145364)
  - [Web 安全测试之 XSS - Cross Site Scripting, 跨站脚本攻击](https://www.cnblogs.com/TankXiao/archive/2012/03/21/2337194.html)
  - [前端安全系列之二：如何防止CSRF攻击？ - Cross-site request forgery, 跨站请求伪造](https://juejin.im/post/5bc009996fb9a05d0a055192)

#### React

- [Should I use shouldComponentUpdate?](http://jamesknelson.com/should-i-use-shouldcomponentupdate/)
- [React 基本原理及性能优化](https://segmentfault.com/a/1190000015648248)
- [React 性能优化总结](https://segmentfault.com/a/1190000007811296)
- [深入理解 React 底层实现原理](https://zhuanlan.zhihu.com/p/101507773)

#### 其他

- [4 类 JavaScript 内存泄露及如何避免](https://juejin.im/entry/5742dc3471cfe4006c4e6c45/view)
- [开开心心做几道 JavaScript 机试题](https://segmentfault.com/a/1190000005828394)
- [44个 Javascript 变态题解析 (上\下)](http://ourjs.com/detail/5761040488feaf2d031d2526?utm_source=tuicool&utm_medium=referral)
- [20个 Js 变态题解析](https://segmentfault.com/a/1190000005988554)
- [JavaScript 数组乱序 - 洗牌问题](https://github.com/lessfish/underscore-analysis/issues/15)
- [十几道含答案的大厂面试题总结](https://juejin.im/post/5e096d63e51d4558381e9906)
- [*JavaScript Questions*](https://github.com/lydiahallie/javascript-questions)

- deepcopy 实现
  - [What is the most efficient way to deep clone an object in JavaScript?](https://stackoverflow.com/questions/122102/what-is-the-most-efficient-way-to-deep-clone-an-object-in-javascript)
  - [lodash.cloneDeep](https://github.com/lodash/https://github.com/lodash/lodash/blob/master/cloneDeep.js)
  - [deepcopy.js](https://github.com/sasaplus1/deepcopy.js)
- Immutable.js
  - [为什么用 Immutable.js 代替普通 js 对象？](https://zhuanlan.zhihu.com/p/29983598)
  - [facebook immutable.js 意义何在，使用场景？](https://www.zhihu.com/question/28016223)
  - [为什么需要 Immutable.js](http://zhenhua-lee.github.io/react/Immutable.html)

```javascript
JSON.parse(JSON.stringify(obj)) // hack
// Issues with Date() when using JSON.stringify() and JSON.parse()
// https://stackoverflow.com/questions/11491938/issues-with-date-when-using-json-stringify-and-json-parse/
```

- 防抖`debounce`: 事件被触发后 N 秒内不能重复执行。如果执行，则 N 重新计时
- 节流`throttle`: 如果持续触发一个事件，则在一定的时间内只执行一次事件

#### 扩展阅读

- [Future JavaScript: what is still missing?](https://2ality.com/2019/01/future-js.html)
  - [距离最好的编程语言，JavaScript 还缺些什么？](https://www.infoq.cn/article/Sv8He1JZNj_qZgOxL7zg)
- [ECMAScript 2019: the final feature set](https://2ality.com/2018/02/ecmascript-2019.html)
- [What's New in ES2019: Array flat and flatMap, Object.fromEntries](http://thecodebarbarian.com/whats-new-in-es2019-flat-flatmap-catch.html)
- [New ES2018 Features Every JavaScript Developer Should Know](https://css-tricks.com/new-es2018-features-every-javascript-developer-should-know/)
- [Functional-Light JavaScript](https://github.com/getify/Functional-Light-JS)
- [For vs forEach() vs for/in vs for/of in JavaScript](http://thecodebarbarian.com/for-vs-for-each-vs-for-in-vs-for-of-in-javascript.html)

### Redis

#### 知识点

- [Redis 基础](https://juejin.im/post/5db66ed9e51d452a2f15d833)
- [Redis 常见面试题（带答案）](https://juejin.im/post/5dcaebea518825571f5c4ab0)
- [Redis 避免缓存穿透的利器之 BloomFilter](https://juejin.im/post/5db69365518825645656c0de)

#### 其他

- [谈谈 Redis 的 SETNX](https://www.jianshu.com/p/8b3130229515)
- [Redis 的 KEYS 命令引起 RDS 数据库雪崩，RDS 发生两次宕机，造成几百万的资金损失](https://mp.weixin.qq.com/s/SGOyGGfA6GOzxwD5S91hLw)
- [Redis 和 Memcache 的区别总结](https://www.cnblogs.com/aspirant/p/8883871.html)

### 计算机

- [简单介绍 CPU 的工作原理](https://www.cnblogs.com/onepixel/p/8724526.html)

### 计算机网络

- [RESTfulAPI](https://github.com/aisuhua/restful-api-design-references)

> http 数据分隔 CLRF(\r\n)

- [扒一扒 HTTP 的构成](http://mrpeak.cn/blog/http-constitution/)
- [从输入 URL 到页面加载完成的过程中都发生了什么事情？](http://fex.baidu.com/blog/2014/05/what-happen/)
- [HTTP 状态码](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Status)
- [一文读懂一台计算机是如何把数据发送给另一台计算机的](https://zhuanlan.zhihu.com/p/58327059)

- [ARP 协议在同网段及跨网段下的工作原理](https://zhuanlan.zhihu.com/p/148644458)
- [每天都在用的 Ping 命令，它到底是什么？](https://zhuanlan.zhihu.com/p/45110873)
- [ICMP 在 OSI 第几层？有人说二层(链路层) 有人说三层(网络层) 还有人说四层(传输层)?](https://www.zhihu.com/question/31002474)

#### TCP/UDP

TCP/UDP/IP

- [**TCP/IP 协议知识科普**](https://www.cnblogs.com/xuanku/p/tcpip.html)
- [深入浅出 TCP/IP 协议栈](https://www.cnblogs.com/onepixel/p/7092302.html)
- [**面试官，不要再问我三次握手和四次挥手**](https://juejin.im/post/5d9c284b518825095879e7a5)
- [通俗大白话来理解 TCP 协议的三次握手和四次分手](https://github.com/jawil/blog/issues/14)
- [TCP 的那些事儿（上）](https://coolshell.cn/articles/11564.html)
- [Mac 地址会不会有重复的？怎么做到全球唯一的？如果网卡作废了，那么 Mac 地址回收吗？](https://wukong.toutiao.com/question/6681530607454912776/)
- [TCP/IP、Http、Socket 的区别](https://mp.weixin.qq.com/s?__biz=MjM5OTMxMzA4NQ==&mid=403550414&idx=2&sn=b466e4a4a469782a1374095be4bd3036&scene=0#wechat_redirect)
- [如何通俗地解释一下 TCP/UDP 协议和 HTTP、FTP、SMTP 等协议之间的区别？](https://www.zhihu.com/question/20583641)
- [TCP 为什么需要第三次握手？第三次握手失败了会怎么样？](https://www.nowcoder.com/questionTerminal/d88f9db98e034c158b51bf362dff91e3)
- [TCP 流量控制中的滑动窗口大小、TCP 字段中16位窗口大小、MTU、MSS、缓存区大小有什么关系？](https://www.zhihu.com/question/48454744)

调优

- [Linux 下 Http 高并发参数优化之 TCP/IP 基础](https://kiswo.com/article/1016)
- [理解 TIME_WAIT](http://www.firefoxbug.com/index.php/archives/2795/)
- [Linux 下 Http 高并发参数优化之 TCP 参数](https://kiswo.com/article/1017)
- [Linux TCP/IP 协议栈调优](https://colobu.com/2014/09/18/linux-tcpip-tuning/)

- [不要在 Linux 上启用 net.ipv4.tcp_tw_recycle 参数](http://www.cnxct.com/coping-with-the-tcp-time_wait-state-on-busy-linux-servers-in-chinese-and-dont-enable-tcp_tw_recycle/)
- [tcp_tw_reuse、tcp_tw_recycle 使用场景及注意事项](https://www.cnblogs.com/lulu/p/4149312.html)

TCP 连接和挥手过程：

![tcp 连接和挥手过程](https://images.cnblogs.com/cnblogs_com/xuanku/688508/o_tcp_status.png)

`TIME_WAIT`是主动关闭方在收到被动关闭方发的`FIN`包之后处于的状态, 这个包是主动关闭方收到的最后一个包了, 在收到这个包之后还不能直接就把连接给关闭了, 还得等待一段时间才能关闭, 等待时间为`2MSL`。

为什么要等待一段时间呢? 主要是两个原因:

1. 在收到最后一个包之后主动关闭方还得发一个`ACK`回去, 这个`ACK`可能会丢包, 如果丢包, 对方还需要重新发最后一个`FIN`包, 如果收到重新发过来的`FIN`包的时候这边连接已经关闭, 则会导致连接异常终止;
2. 不过第 1 点也不会造成太大的问题, 毕竟数据已经正常交互了。但是有另外一点风险更高, 就是如果不等待`2MSL`的话, 那么如果正好一个新连接又建立在相同的端口上, 那么上次的`FIN`包可能因为网络原因而延时的包，这个时候才送达该端口, 导致下一次连接出现问题;

所以一定要有一个`TIME_WAIT`的状态等待一段时间, 等待的`MSL`时间`RFC`上面建议是 2 分钟

但是如果你的服务是一个高并发短连接服务, `TIME_WAIT`可能会导致连接句柄被大量占用, 而你又相信服务内部是一个非常稳定的网络服务, 或者即使有两个连接交互出现故障也可以接受或者有应用层处理, 不希望有那么多的`TIME_WAIT`状态的连接, 一般有两种方式:

1. 在建立连接的时候使用`SO_REUSEADDR`选项
2. 在`/etc/sysctl.conf`中加入如下内容:

```bash
# 表示开启 TCP 连接中 TIME-WAIT sockets 的快速回收，默认为 0，表示关闭
net.ipv4.tcp_tw_recycle = 1
# 表示开启重用。允许将 TIME-WAIT sockets 重新用于新的 TCP 连接，默认为 0，表示关闭
net.ipv4.tcp_tw_reuse = 1
# 对于本端断开的 socket 连接，TCP 保持在 FIN-WAIT-2 状态的时间。对方可能会断开连接或一直不结束连接或不可预料的进程死亡。默认值为 60 秒
# 即 MSL。断开连接四次挥手时，最后会等待 2MSL 后释放文件句柄
net.ipv4.tcp_fin_timeout = 1
# 在每个网络接口接收数据包的速率比内核处理这些包的速率快时，允许送到队列的数据包的最大数目
net.core.netdev_max_backlog = 4000
```

然后执行`/sbin/sysctl -p`生效参数

#### 扩展阅读

- [高性能网络编程(一)：单台服务器并发 TCP 连接数到底可以有多少](http://www.52im.net/thread-561-1-1.html)
  - [为什么 QQ 用的是 UDP 协议而不是 TCP 协议？](http://www.52im.net/thread-279-1-1.html)
  - [移动端 IM/推送系统的协议选型：UDP 还是 TCP？](http://www.52im.net/thread-33-1-1.html)
- [高性能网络编程(二)：上一个10年，著名的 C10K 并发连接问题](http://www.52im.net/thread-566-1-1.html)
  - [聊聊 C10K 问题及解决方案](https://my.oschina.net/xianggao/blog/664275)
  - [程序员怎么会不知道 C10K 问题呢？](https://medium.com/@chijianqiang/%E7%A8%8B%E5%BA%8F%E5%91%98%E6%80%8E%E4%B9%88%E4%BC%9A%E4%B8%8D%E7%9F%A5%E9%81%93-c10k-%E9%97%AE%E9%A2%98%E5%91%A2-d024cb7880f3)
  - [2000 年问题（千年虫问题）](https://zh.wikipedia.org/wiki/2000%E5%B9%B4%E9%97%AE%E9%A2%98)
- [高性能网络编程(三)：下一个 10 年，是时候考虑 C10M 并发问题了](http://www.52im.net/thread-568-1-1.html)
- [高性能网络编程(四)：从 C10K 到 C10M 高性能网络应用的理论探索](http://www.52im.net/thread-578-1-1.html)
- [高性能网络编程(五)：一文读懂高性能网络编程中的 I/O 模型](http://www.52im.net/thread-1935-1-1.html)
- [高性能网络编程(六)：一文读懂高性能网络编程中的线程模型](http://www.52im.net/thread-1939-1-1.html)
- [高性能网络编程经典：《The C10K problem(英文)》[附件下载]](http://www.52im.net/thread-560-1-1.html)

#### HTTPS

- [HTTPS 基本过程](https://hit-alibaba.github.io/interview/basic/network/HTTPS.html)
- [**HTTPS 科普扫盲帖**](https://www.cnblogs.com/chyingp/p/https-introduction.html)

连接基本过程：

1. 客户端请求服务端，服务端给出自己证书
2. 浏览器从证书中拿出服务端公钥 A
3. 浏览器生成自己的对称密钥 B，用公钥 A 加密 B 后传输给服务端
4. 服务端用私钥 C 解密，获取到对称密钥 B
5. 之后两端通讯使用对称密钥 B 加密

证书合法性检查：

1. 首先，证书中包含：签发机构 CA、数字签名（用 CA 私钥加密摘要）、证书持有者公钥 A、签名的 hash 算法
  - 数字签名的由来：明文 -> hash 运算 -> 摘要 -> CA 私钥加密 -> 数字签名
2. 其次，浏览器内置了 CA 的根证书，包含 CA 的公钥
3. 浏览器收到服务端证书以后：
  - 检查证书颁发机构是否存在，然后找到 CA 证书、CA 公钥
  - 用 CA 公钥解密数字签名，解出被加密的证书摘要 AA
  - 用证书中提供的 hash 算法，计算出当前证书的摘要 BB
  - 比较 AA 和 BB
  - 以上有任意一步失败，则会认为证书被伪造

#### SSH

- [图解 SSH 原理](https://www.jianshu.com/p/33461b619d53)

#### DNS/CDN、代理

- [CDN 原理简析](https://juejin.cn/post/6844903873518239752)
- [反向代理为何叫反向代理？](https://www.zhihu.com/question/24723688)
- [正向代理与反向代理【总结】](https://www.cnblogs.com/anker/p/6056540.html)
- [TTL 和 DNS TTL 的区别](https://www.cnblogs.com/onepixel/p/7159529.html)
- [五分钟看懂 Nginx 负载均衡](https://juejin.cn/post/6844904106541203464)
- [Nginx 负载均衡的5种策略](https://segmentfault.com/a/1190000014483200)

#### 网络攻击

<!-- TODO: -->

- [和安全有关的那些事(非对称加密、数字摘要、数字签名、数字证书、SSL、HTTPS及其他)](https://blog.csdn.net/bluishglc/article/details/7585965)

### 算法和数据结构

#### 算法

- [Javascript Array.sort implementation?](https://stackoverflow.com/questions/234683/javascript-array-sort-implementation)
- [js 中 sort 函数的底层实现机制？](https://segmentfault.com/q/1010000007133473)
- [十大经典排序算法（动图演示）](https://www.cnblogs.com/onepixel/p/7674659.html)
- [一致性 hash 算法释义](https://www.cnblogs.com/haippy/archive/2011/12/10/2282943.html)

#### 难点

- [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)
- [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

#### 数据结构

- [《吊打面试官》系列 - HashMap](https://juejin.im/post/5dee6f54f265da33ba5a79c8)

### 架构

#### 消息队列

- [消息队列基础](https://juejin.im/post/5dd3ff85e51d453fe34dfcc5)
- [分布式事务、重复消费、顺序消费](https://juejin.im/post/5dda9e7e6fb9a07aae2a3778)

#### 微服务

- [微服务杂谈](https://www.rowkey.me/blog/2019/05/30/msa/)
- [微服务十二要素](https://12factor.net/zh_cn/codebase)

#### 稳定性

- [分布式事务：两阶段提交与三阶段提交](https://segmentfault.com/a/1190000012534071)
- [分布式一致性之两阶段提交协议、三阶提交协议](https://zhuanlan.zhihu.com/p/35616810)

### Linux

- [介绍 Linux 文件系统：这些目录都是什么鬼？](https://mp.weixin.qq.com/s/kJx07mbQQExV3JUGJo4nYw)
- [Learn Enough Command Line to Be Dangerous](https://www.learnenough.com/command-line-tutorial/basics)
- [70个经典的 Shell 脚本面试问题](http://www.imooc.com/article/1131)

### 其他

- [系统设计入门](https://github.com/donnemartin/system-design-primer/blob/master/README-zh-Hans.md)
- [秒杀系统设计与实现](https://github.com/qiurunze123/miaosha)
- [码农翻身全年文章精华](https://mp.weixin.qq.com/s?__biz=MzAxOTc0NzExNg==&mid=2665513504&idx=1&sn=25dd6420e3056101dd3f6fdaedacaa2a&chksm=80d67a63b7a1f37572a5159ff6f53810467c15c8beec94770e8360c45f45036360d77755ee78&scene=21#wechat_redirect)
- [这些知识决定了程序员的上限](https://www.rowkey.me/blog/2019/04/22/upforprogrammer/)
- [Interview Map](https://github.com/InterviewMap/CS-Interview-Knowledge-Map)
- [当···时发生了什么？](https://github.com/skyline75489/what-happens-when-zh_CN)
- [hacker-laws-zh](https://github.com/nusr/hacker-laws-zh)

React 虚拟 DOM

```javascript
class Test {
  constructor() {
    this.echo = () => {
      console.log('echo in constructor')
    }
  }

  echo() {
    console.log('echo')
  }
}

Test.echo // error
new Test().echo() // echo in constructor
```
