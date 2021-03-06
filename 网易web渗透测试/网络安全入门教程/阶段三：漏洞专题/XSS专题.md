# XSS攻击

```XSS攻击专题概述
XSS攻击专题概述--跨站脚本攻击过程
    1、恶意攻击者通过Email或HTTP将构造好的url发送给普通用户
    2、普通用户在浏览器中浏览该url
    3、浏览器执行脚本后，返回数据
    4、在普通用户毫不知情的情况下，脚本将其cookie等信息发送给攻击者
    5、攻击者使用盗取来的cookie等敏感信息用来伪造用户
```

```XSS攻击定义、分类及危害
xss攻击的定义
    跨站脚本攻击（Cross Site Scriping），为不和层叠样式表（Cascdaing Style Sheets，CSS）的缩写混淆，
    故将跨站脚本攻击缩写为xss。
    恶意攻击者往Web页面里插入恶意Script代码，当用户浏览该页时，嵌入其中Web里面的Script代码会被执行，从而达
    到恶意攻击用户的特殊目的。
Xss攻击的危害
    这些危害包括但不局限于：
    盗取管理员或普通用户cookie、session；
    读取、篡改、添加、删除敏感数据；
    网站挂马；
    非法转账；
    控制受害者及其向其他网站发起攻击···
```

```XSS攻击常见编码及绕过方式
按攻击方式分类
    ·反射型XSS：只是简单地把用户数的数据反射给浏览器，黑客需要诱使用户点击链接。
    也叫做“非持久型XSS”（Non-persistent XSS）。
    ·存储型XSS：把用户输入的数据“存储”在服务器端。这种XSS具有很强的稳定性。比较常见的一个场景是，
    攻击者写下一篇包含恶意JavaScript代码的文章，文章发表后，所有访问该博客文章的用户，都会在他们
    的浏览器中执行这段恶意的Javascript代码。黑客把恶意的脚本保存在服务器端。存储型XSS也叫持久型XSS。
    ·DOM based XSS：从效果上来说也是一种反射型XSS。通过修改页面的DOM节点形成的XSS，称之为DOM Based XSS）。
XSS攻击常见编码
    ·URL编码、JS编码、CSS编码、复合编码、字符编码
常见编码划分
    ·URL编码：只是简单一个百分号和该字符的ASCII编码所对应的2位十六位进制数字，
    例如“/”的URL编码为%2F（一般大写，但不强求）
    ·字符编码：把十进制、十六进制ASCII码或Unicode字符编码，样式为“&#数值;”，例如“<”可编码为“”和“”>
    ·复合编码：所谓复合编码，也就是说输出的内容输出在多个环境中；
    CSS编码：用一个反斜线（\）后面跟1~6位的十六进制水准，例如e可以编码为"\65"、"65"或"\u0065"
    JS编码：如"e"编码为"\145"、"\x65"或"\u0065"
```


```XSS攻击常见测试语句
        常见测试语句：
        ·<script>alert('test');</script>
        ·<svg onload=alert('test')>
        ·
        ·<IMG SRC=# "width:expression(alert('test'));">
        ·<BODY ONLOAD=alert('test')>
        ·<DIVSTYLE="width:expression(alert('test'));" >
        ·<BASE HREF="javascript.:alert('test');//">
```


