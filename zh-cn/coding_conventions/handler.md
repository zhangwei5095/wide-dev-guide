# Handler 包装

在 ````main.go```` 中加入新的 HTTP Handler 时需要使用 ````handlerWrapper```` 函数进行包装，以便做一些共性处理：

* panic recover
* 请求处理计时




