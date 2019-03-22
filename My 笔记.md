# My 笔记

##   **修改多个后缀名命令**

#### `ren *.php *.html`

---

## **node.js创建一个简单的服务**

```javascript
// 1. 加载 http 核心模块
var http = require('http')

// 2. 创建一个 web 服务器
var server = http.createServer()

// 3. 注册request 请求事件 当客户端请求过来 就会触发 request 
// 事件 然后执行第二个参数 回调处理
server.on('request', function (request, response) {
	// console.log('我收到了, 请求路径是' + request.url)
	// response.write('hello')
	// response.end()

	// 上面的方式比较麻烦，推荐使用更简单的方式，直接 end 的同时返回响应
	// response.end('hello')

	// 根据不同的请求路径发送不同的响应结果
	// 1. 获取请求路径
	//   request.url 获取到的端口号之后的那一部分 
	// 2. 判断路径处理响应
	var url = request.url
	if (url === '/') {
		response.end('index page')
	} else if (url === '/login') {
		response.end('login page')
	} else {
		response.end('404 not found')
	}
})

// 4. 绑定端口号， 启动服务器
server.listen(3000, function () {
	console.log('服务器启动成功了，可以通过 http://127.0.0.1:3000/ 来进行访问')
})

```

## **服务端设置响应头**

+ `response.setHeader('Content-Type', 'text/plain'; charset=utf-8)`
+ ``response.setHeader('Content-Type', 'text/html'; charset=utf-8)``

## **Content-Type 类型**

[查询地址](https://tool.oschina.net/commons)

