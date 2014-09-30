# WebSocket

WebSocket 用于后端推送数据给前端：

* 输出通道````OutputWS````
* 通知通道````NotificationWS````
* Shell 通道````ShellWS````
* _会话通道_````SessionWS````

通道和[会话](session.md)一对一关联，也就是说如果用户新开浏览器 tab，则新建通道和其关联。

其中_会话通道_用于[会话管理](../session_mgmt/wide.md)，后面会单独介绍。
