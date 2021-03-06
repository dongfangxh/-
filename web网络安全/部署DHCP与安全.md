# 部署DHCP与安全

ipconfig /release(释放ip，或者改为手动配置ip，也可以释放租约)

ipconfig /renew(从新获取ip包**未获取IP时**)

ipconfig /renew(手动续约**获取ip时**)

##选项优先级

作用域选项>服务器选项

**当服务器上有多个作用域时，可以在服务器选项上设置DNS服务器**

##DHCP攻击与防御

1）攻击DHCP服务器：频繁的发送伪装DHCP请求，直到将dhcp地址池耗尽

防御：在交换机上(管理型)的端口上做动态MAC地址绑定

2）伪装DHCP服务器攻击：hack通过将自己部署的DHCP服务器，为客户机提供非法IP地址

防御：在交换机(管理型)上，除合法的DHCP服务器所在接口外，全部设置为禁止发送DHCP offer包