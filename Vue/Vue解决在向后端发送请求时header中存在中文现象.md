### Vue解决在向后端发送请求时header中存在中文现象

前端发送用编码：

```js
// 编码
encodeURIComponent(str)
// 解码
decodeURIComponent(str)
```

后端接收后解码：

```java
//编码
java.net.URLEncoder.encode(token,"UTF-8")
//解码
java.net.URLDecoder.decode(token,"UTF-8")
```

