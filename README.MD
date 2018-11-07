### Get请求的接收

###### 在koa2中GET请求通过request接收，但是接受的方法有两种：query和querystring。
- query：返回的是格式化好的参数对象。
- querystring：返回的是请求字符串。

###### 除了在ctx.request中获取Get请求外，还可以直接在ctx中得到GET请求。ctx中也分为query和querystring。

### POST请求如何接收

###### 对于POST请求的处理，Koa2没有封装方便的获取参数的方法，需要通过解析上下文context中的原生node.js请求对象req来获取

###### 获取Post请求的步骤
1. 解析上下文ctx中的原生nodex.js对象req。
2. 将POST表单数据解析成query string-字符串.(例如:user=jspang&age=18)
3. 将字符串转换成JSON格式

###### ctx.request和ctx.req的区别
- ctx.request:是Koa2中context经过封装的请求对象，它用起来更直观和简单。
- ctx.req:是context提供的node.js原生HTTP请求对象。这个虽然不那么直观，但是可以得到更多的内容，适合我们深度编程。

###### ctx.method 得到请求类型

- Koa2中提供了ctx.method属性，可以轻松的得到请求的类型，然后根据请求类型编写不同的相应方法，这在工作中非常常用.
