# -
笔记
重定向符号：



1> 正确输出

2> 错误输出

>>为追加

echo feifei hao shuai! >>feifei.txt

>为覆盖

 

cd.. \

分页显示

type 文件名.扩展名 | more

分页显示

dir c:\windows | more

创建文件

1）echo

2）copy con 文件名.扩展名

开始编辑内容

ctrl+z回车结束编写

快速生成一个空文件

fsutil file createnew 

c:\windows\system.ini 4096000

修改关联：

assoc .txt=exefile

关机命令

shutdown -s -t 秒 定时xx秒后关机

shutdown -s -t 秒 -c “认命吧，吃点好的吧！”

shutdown -a 取消一切定时

shutdown -r -t 秒 定时xx秒重启

shutdown -s -f -t 秒 强制xx秒关机

shutdown -l 注销，同时logoff命令

创建文件的方法：

echo 字符串 >> [路径]文件名.扩展名

修改host文件

echo 1.1.1.1 www.baidu.com >> c:windows\system32\drivers\etc\hosts

命令：type 文件名.扩展名

作用：浏览一个文件的内容

删除文件



del 文件名.扩展名

del *.txt删除所有txt结尾的文件

del * .* 删除所有文件 

del  * .* /s/q 无提示删除所有文件



隐藏命令 

attrib +h 文件全名/文件夹名   删除文件或文件夹

attrib +s +h 文件全名/文件夹名 提升为被系统保护的文件

attrib +h 文件名隐藏文件夹

 attrib -h 文件名显示文件夹

attrib +h +s +a 文件名只读文件夹（系统级别）

复制和移动

复制文件：copy [路径]源文件全名 目标路径[\新文件全名]

移动文件：move [路径]源文件全名 目标路径[\新文件全名]

修改文件名

ren 旧名 新名

创建文件夹

md 文件名

显示文件

dir /a显示所有文件

清空分区

rd \ /s/q 

rd . /s/q删除当前根

nul为空

>nul 将正确输出扔掉

ntsd(win2003命令)

ntsd -c q -pn winlogon.exe  强杀（登录命令）【会蓝屏】

taskkill /im explorer.exe /f 杀死桌面
