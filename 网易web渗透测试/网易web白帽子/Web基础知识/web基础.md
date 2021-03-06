```web
http请求----referer
HTTP Referer：告知服务器该请求的来源(浏览器自动加上)
```

```web开发基础知识
HTML+CSS+JS
HTML结构		HTML+HEAD+BODY
HTML元素		属性：元素的额外信息
标签属性：name,id,class,···
DOM：文档对象模型 Document Object Model      将文档转换为--树结构--
```

```javascript
JS+DOM+BOM

在那些地方可以运行JavaScript？
HTML的<script></script>之间
HTML的时间属性中如``onclick``

JavaScript语法是否很复杂？
JavaScript遵循ECMAScript标准
ECMAScript包含了语法规范等
语法很容易和掌握
借用了C、Java的语法

JavaScript HTML 


DOM可以在页面操作HTML

如何获取一个HTML元素内容？
第一步,获取元素
getElementByld():通过id获取元素
第二步,获取元素内容
.innerHTML:获取元素内容
TIPS：
alert()方法再JavaScript中表示弹出一个
警告框，可以用来展示信息

如何修改一个HTML元素内容？
第一步,获取元素
getElementByld():通过id获取元素
第二步,获取元素内容
.innerHTML:通过id获取元素

修改一个HTML from元素内容
第一步,选定登录框元素,找到
id=urs-ls-form
第二步,获取urs-lg-from的元素
内容，并修改为一个html的iframe框架(使用Console)

如何创建动态的HTML元素内容？
document。write()

document.write写入html内容
document.write写入当前时间
document.write(Date())
document.write写入iframe

如何让页面增加点互动？
当我们点击时，页面内容改变
点击事件<-->onclick

以上使用JavaScript访问和操作HTML就是JavaScript DOM的操作
DOM本质
连接web页面和编程语言
Javascript+DOM
访问和操作HTML文档的标准方法


获取浏览器信息，操作浏览器行为Javascript BOM

如何让浏览器来警告用户？
警告弹窗alert()
确认弹窗confirm()
提示弹窗prompt()
TIPS：
常用于简单的调试和信息展示。
如xss漏洞的测试

如何从浏览器获取用户的Cookie？
Cookie讲解
通常是服务器发给客户端的一小段文本信息
常见场景
用户输入用户名和密码成功登陆网站后，网站会产生一个cookie给用户，当前用户凭证
这个凭证cookie就相当于我们的要是我们每次访问网站的时候浏览器都会带上钥匙(cookie)

获取Cookie
document.cookie
写入cookie
document.cookie="写入值"
问题：
alert(document.cookie)是什么意思？

还有其他浏览器获取和操作行为？
获取浏览器屏幕信息
window.screen
获取/控制用户页面URL
window.location
获取访问者浏览器信息
window.navigator
操作浏览器窗口：window open,close

BOM		浏览器对象模型  Browser Object Model
```

