# Wide 会话

Wide 不是一个 Web 网站，它对服务器端的状态管理有特殊的需求。

## 生命周期
在前面我们提到过 Wide 会话和浏览器 tab 的[关系](key_designs/session.md)，这定义了 Wide 会话的生命周期和浏览器 tab 是一致的：

* 新建 tab 时（刷新也认为是新建），服务器端创建会话
* tab 处于打开时，服务器端维持会话
* 关闭 tab 时，服务器端销毁会话

## 会话状态

一个 Wide 会话包含如下信息：

* 关联的*HTTP 会话*
* 关联的*事件队列*
* 关联的*运行进程集*
* 当前会话状态：Active/Closed
* 创建时间
* 最近一次使用时间：收到事件、运行进程都会更新这个时间

销毁一个会话时，需要将其相关的资源回收，避免泄漏。

## 实现

服务器端使用 WebSocket 建立同 tab 的通讯通道，通道关闭时销毁服务器端会话。
