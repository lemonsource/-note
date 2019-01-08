# Ubantu浏览器配置ss并开机启动
**先卸载**
1. `sudo pip uninstall shadowsocks`

**再安装ss**
2. `sudo pip install shadowsocks`

**配置ss启动文件**

`sudo gedit /etc/shadowsocks.json`xuanxiang
```
{
"server":"",
"server_port":1024,
"local_port":1080,
"password":"",
"timeout":600,
"method":"aes-256-cfb"xuanxiang
}
```
**前端启动**

`sslocal -c /etc/shadowsocks.json`

**后台启动**

`sslocal -c /etc/shadowsocks.json -d start`

### 设置开机启动
**打开rc.local文件，在exit 0前面添加一条命令**

`sudo gedit /etc/rc.local`

**文件内容**
```sudo
sudo sslocal -c /etc/shadowsocks.json
exit 0
```

## Google浏览器安装插件SO

1. **安装插件SwitchyOmega，下载地址<a href = "https://github.com/FelisCatus/SwitchyOmega/releases/" >SwitchyOmega</a>**
2. **浏览器打开chrome://extensions/**
3. **代理协议选择SOCKS5，地址127.0.0.1，端口默认为1080**
4. **应用选项**