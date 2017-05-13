# Shadowsocks Python版一键安装脚本
## 本脚本适用环境:  
系统支持：CentOS 6，7，Debian，Ubuntu  
内存要求：≥128M  
[点击查看教程](https://teddysun.com/342.html "卖假货的学长推荐，点了不后悔，哈哈！")  
![](https://teddysun.com/wp-content/uploads/2014/shadowsocks.png)  
## 关于本脚本：
一键安装 Python 版 Shadowsocks 的最新版，同时安装了 Python 包管理工具 pip。
友情提示：如果你有问题，请先参考这篇《Shadowsocks Troubleshooting》  
默认配置：  
服务器端口：自己设定（如不设定，默认为8989）  
客户端端口：1080  
密码：自己设定（如不设定，默认为teddysun.com）  
备注：脚本默认创建单用户配置文件，如需配置多用户，安装完毕后参照下面的教程 sample 手动修改配置文件后重启即可。  
客户端下载：  
https://github.com/shadowsocks/shadowsocks-windows/releases   
## 使用方法：
使用root用户登录，运行以下命令：  
>wget --no-check-certificate -O shadowsocks.sh      https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh  
 chmod +x shadowsocks.sh  
  ./shadowsocks.sh 2>&1 | tee shadowsocks.log
 
 安装完成后，脚本提示如下：  
 >Congratulations, shadowsocks install completed!  
  Your Server IP:your_server_ip  
  Your Server Port:your_server_port  
  Your Password:your_password  
  Your Local IP:127.0.0.1  
  Your Local Port:1080  
  Your Encryption Method:aes-256-cfb  

  Welcome to visit:https://teddysun.com/342.html  
  Enjoy it!  
 ## 使用命令进行相关操作：
启动：/etc/init.d/shadowsocks start  
停止：/etc/init.d/shadowsocks stop  
重启：/etc/init.d/shadowsocks restart  
状态：/etc/init.d/shadowsocks status  
## 卸载方法：
使用root用户登录，运行以下命令：
>./shadowsocks.sh uninstall  

## 单用户配置文件：
### 配置文件路径：/etc/shadowsocks.json

> {
    "server":"0.0.0.0",
    "server_port":8989,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"yourpassword",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
  }


## 多用户多端口配置文
### 配置文件路径：/etc/shadowsocks.json

> {
    "server":"0.0.0.0",
    "local_address":"127.0.0.1",
    "local_port":1080,
    "port_password":{
         "8989":"password0",
         "9001":"password1",
         "9002":"password2",
         "9003":"password3",
         "9004":"password4"
    },
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
  }
