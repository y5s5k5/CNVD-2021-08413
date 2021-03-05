环境:Windows10 x64   
软件官网:https://pinyin.sogou.com  
下载地址:  
https://ime.sogoucdn.com/82342a54e50afd87d1932cabd4a36c89/60063f54/dl/index/1609387427/sogou_pinyin_100a.exe  

漏洞进程名:SGTool.exe  
漏洞文件名: C:\Users\管理员用户\AppData\LocalLow\SogouPY  
影响版本:10.0.0.4  
关联厂商:搜狗  

此漏洞的根本原因是因为 C:\Users\管理员用户名\AppData\LocalLow\SogouPY不安全的控制造成的   

SogouPY文件并没有默认继承管理员文件夹的权限，设置了一个明确的DACL：该文件和其子文件全部都被普通用户完全控制，并且在创建这些文件没有判断文件解析点。

所以即使被符号链接劫持其中一个子文件到C:\Windows\system32 下也被用户完全控制。
