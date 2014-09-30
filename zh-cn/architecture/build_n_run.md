# 构建 & 运行

![](https://cloud.githubusercontent.com/assets/873584/4389219/3642bc62-43f3-11e4-8d1f-06d7aaf22784.png)

* 一个浏览器 tab 对应一个 Wide 会话
* 通过 WebSocket 进行程序执行输出推送


1. 客户端浏览器发送 ````Build```` 请求
2. 服务器使用 ````os/exec```` 执行 ````go build```` 命令<br/>
   2.1. 生成可执行文件
3. 客户端浏览器发送 ````Run```` 请求
4. 服务器使用 ````os/exec```` 执行文件<br/>
   4.1. 生成进程<br/>
   4.2. 运行结果输出到 WebSocket 通道
5. 客户端浏览器监听 ````ws.onmessage```` 到消息后做展现
