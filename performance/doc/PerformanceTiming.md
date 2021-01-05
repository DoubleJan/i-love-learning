# PerformanceTiming

> `PerformanceTiming` 接口是为了保证向后兼容而存在的传统接口，已不在标准内。

## 一 概述

`PerformanceTiming` 接口提供了在页面加载和使用时的各种性能计时信息。通过 `window.performance.timing` 获得一个实例对象。

## 二 属性

> PerformanceTiming 接口的所有属性都是只读的，且没有任何继承属性，由于所有属性均是某个时间点，因此值类型都是 无符号 long long 类型（double）

### (1) PerformanceTiming.navigationStart

`PerformanceTiming.navigationStart` 表示同一个浏览器上下文中，上一个文档卸载结束的 UNIX 时间戳。如果没有上一个文档，这个值与 `PerformanceTiming.fetchStart` 相同。

### (2) PerformanceTiming.unloadEventStart

`PerformanceTiming.unloadEventStart` 表示 `unload` 事件抛出时的 UNIX 时间戳。如果没有上一个文档，或者重定向中的一个与当前文档不同源，该值为 `0`。

### (3) PerformanceTiming.unloadEventEnd

`PerformanceTiming.unloadEventEnd` 表示 `unload` 事件处理完成时的 UNIX 时间戳。如果没有上一个文档，或者重定向中的一个与当前文档不同源，该值为 `0`。

### (4) PerformanceTiming.redirectStart

`PerformanceTiming.redirectStart` 表示第一个 HTTP 重定向开始时的 UNIX 时间戳。如果没有重定向，或者重定向中的一个不同源，该值为 `0`。

### (5) PerformanceTiming.redirectEnd

`PerformanceTiming.redirectEnd` 表示最后一个 HTTP 重定向完成时（即最后一个 HTTP 响应的最后一个比特被接收到的时间）的 UNIT 时间戳。如果额米有重定向，或者重定向中的一个不同源，该值为 `0`。

### (6) PerformanceTiming.fetchStart

`PerformanceTiming.fetchStart` 表示浏览器准备好用 HTTP 请求来获取文档的 UNIX 时间戳。这个时间早于检查应用缓存。

### (7) PerformanceTiming.domainLookupStart

`PerformanceTiming.domainLookupStart` 表示域名查询开始的 UNIX 时间戳。如果使用了持续连接，或者这个信息被存储到了缓存或本地资源，那么该值与 `PerformanceTiming.fetchStart` 相同。

### (8) PerformanceTiming.domainLookupEnd

`PerformanceTiming.domainLookupEnd` 表示域名查询结束的 UNIX 时间戳。如果使用了持续连接，或者这个信息被存储到了缓存或本地资源，那么该值与 `PerformanceTiming.fetchStart` 相同。

### (9) PerformanceTiming.connectStart

`PerformanceTiming.connectStart` 表示 HTTP 请求开始向服务器发送时的 UNIX 时间戳。如果使用持久连接，则该值与 `PerformanceTiming.fetchStart` 相同。

### (10) PerformanceTiming.connectEnd

`PerformanceTiming.connectEnd` 表示浏览器与服务器之间的连接建立（即握手与认证等过程全部结束）的 UNIX 时间戳。如果使用持久连接，则该值与 `PerformanceTiming.fetchStart` 相同。

### (11) PerformanceTiming.secureConnectionStart

`PerformanceTiming.secureConnectionStart` 表示浏览器与服务器开始安全链接的握手时的 UNIX 时间戳。如果当前网页不要求安全链接，该值为 `0`。

### (12) PerformanceTiming.requestStart

`PerformanceTiming.requestStart` 表示浏览器向服务器发送 HTTP 请求时的 UNIX 时间戳。

### (13) PerformanceTiming.responseStart

`PerformanceTiming.responseStart` 表示浏览器从服务器收到（或从本地缓存读取）第一个字节时的 UNIX 时间戳。如果传输层从开始请求后失败并连接被重开，该值会被重置为新的请求的相应的时间。

### (14) PerformanceTiming.responseEnd

`PerformanceTiming.responseEnd` 表示浏览器从服务器收到（或从本地缓存读取，或从本地资源读取）最后一个字节时（如果在此之前HTTP连接已经关闭，则返回关闭的时间）的 UNIX 时间戳。

### (15) PerformanceTiming.domLoading

`Performance.domLoading` 表示当前网页 `DOM` 结构开始解析时（即 `Document.readyState` 属性变为 `loading`，相应的 `readystatechange` 事件触发时）的 UNIX 时间戳。

### (16) PerformanceTiming.domInteractive

`Performance.domInteractive` 表示当前网页 `DOM` 结构解析结束，开始加载内嵌资源时（即 `Document.readyState` 的属性为 `interactive`，相应的 `readystatechange` 事件触发时）的 UNIX 时间戳。

### (17) PerformanceTiming.domContentLoadedEventStart

`PerformanceTiming.domContentLoadedEventStart` 表示解析器触发 `DomContentLoaded` 事件，即所有需要被执行的脚本已经被解析时的 UNIX 时间戳。

### (18) PerformanceTiming.domContentLoadedEventEnd

`PerformanceTiming.domContentLoadedEventEnd` 表示所有需要被执行的脚本均已被执行完成时的 UNIX 时间戳。

### (19) PerformanceTiming.domComplete

`PerformanceTiming.domComplete` 表示文档解析完成，即 Document.readyState 变为 `complete` 且相应的 `readystatechange` 事件被触发时的 UNIX 时间戳。

### (20) PerformanceTiming.loadEventStart

`PerformanceTiming.loadEventStart` 表示该文档下，`load` 事件被触发的 UNIX 时间戳。如果还未发送，值为 `0`。

### (21) PerformanceTiming.loadEventEnd

`PerformanceTiming.loadEventEnd` 表示该文档下，`load` 事件结束，即加载事件完成时的 UNIX 时间戳，如果事件未触发或未完成，值为 `0`。

## 三 兼容性

| Chrome | Edge | Firefox | IE | Safari | WebView Android | IOS Safari |
| ------ | ---- | -------- | --- | ----- | -------------- | ---- |
| 6 | 12 | 56 | 9 | 10.1 | `YES` | 10.3 |
