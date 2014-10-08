# 注释

必须遵守：

* m1：优先使用**中文**进行注释
* m2：优先使用行注释 ````//````

尽量遵守（处女座特质）：

* s1：在中文和英文、数字中间插入一个空格
* s2：结尾句号使用英文句点 ````.````
* s3：注释符号后空格再写文本，例如 ````// xxxx```` 而不是 ````//xxxx````
* s4：需要预格式化（````<pre>````）的使用 1 个空格进行缩进

## 示例
````
// HTTP Handler 包装.
// 完成共性处理：
//  1. panic recover
//  2. 请求计时
func handlerWrapper(f func(w http.ResponseWriter, r *http.Request)) func(w http.ResponseWriter, r *http.Request) {
	handler := panicRecover(f)
	handler = stopwatch(handler)

	return handler
}
````
