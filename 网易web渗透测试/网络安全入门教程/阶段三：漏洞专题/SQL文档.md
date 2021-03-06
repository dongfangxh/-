# sql注入

```sql注入定义
sql注入就是利用现有应用程序的特性，攻击者通过在web表单、url等可输入数据的地方插入（恶意）sql语句一并原有sql语句被代库执行。sql命令就是前端应用程序和后端数据库之间的接口。
SQL注入的危害：
这些危害包括但不局限与：
1.数据库敏感信息泄露；
2.网页被篡改、挂马；
3.数据库被恶意操作；
4.服务器被远程控制，被安装后门等
SQL注入常见的分类有
按数据类型分为：数字型（Integer）
			   字符型（String）
返回结果分为：显错注入（Error-Based）
			 盲注（Boolean/Time-Based Blind）
```


```SQL注入的形成：
数据与代码未严格分离；
用户提交的数据参数未作充分检查过滤，即被代入到SQL命令中，改变了原有的SQL命令的“语义”，且成功被数据库执行。
```


```SQL注入常见的过程：
·客户端：参数值等数据被修改
·服务端：未经检查的命令和过滤即将被修改的数据注入到SQL命令中，SQL命令功能被修改
·数据库引擎：执行被修改后的SQL命令
·服务端：将注入的结果返回给客户端
·客户端：根据上一次注入获取到的敏感信息构造注入语句进行进一步注入
```


```SQL注入在渗透测试过程中的作用：
·绕过登陆验证：使用万能密码登录网站后台
·获取敏感数据：获取网站管理员账号、密码等
·文件系统操作：列目录、读取、写入文件等
·注册表操作：读取、写入、删除注册表等
·执行系统命令：远程执行命令
```


```SQL注入漏洞如何寻找：
使用工具：
·优点：自动化、范围广、效率高
·缺点：误报、漏报、测试的方法比较有限
手工测试：
·优点：测试方法灵活
·缺点：效率低、范围窄，因测试者技术水平而异
```


```常见的漏洞扫描工具：
·Safe3wvs、BurpSuite、Appscan、AcunetixWVS
SQL注入漏洞判断依据：
根据客户端返回的结果来进行判断提交的测试语句是否被数据库引擎执行，如果测试语句被执行，则说明村子啊注入漏洞。
```

```sql
·sql测试语句
· 1' or 1=1#
· 1' order by 2 #
· 1' union select 1,2 #
· 1' union select 1,database()#
· 1' union select 1,group_concat(table_name) from information_schema.tables where tbale_schema=database()#
· 1' union select 1,group_concat(column_name) from information_schema.columns where table_name='users'#
· 1' union select group_concat(user_id,first_name),group_concat(password) from u
sers #
```

