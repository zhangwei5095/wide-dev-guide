# 代码辅助

![](https://cloud.githubusercontent.com/assets/873584/4399135/3b80c21c-4463-11e4-8e94-7f7e8d12a4df.png)

* 自动完成
* 查找使用


1. 浏览器客户端发送代码辅助请求
2. Handler 根据请求对应的 HTTP 会话获取用户工作空间
3. 执行 ````gocode````/````ide_stub```` 命令<br/>
   3.1 设置环境变量（${GOPATH} 为用户工作空间路径）<br/>
   3.2 ````gocode```` 命令需要设置参数 ````lib-path````
