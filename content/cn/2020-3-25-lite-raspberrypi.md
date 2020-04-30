---
title: "Lite版树莓派系统使用日志"
date: 2020-03-25T05:38:27Z
draft: true
slug: lite-raspbereypi

---

[下载地址](https://www.raspberrypi.org/downloads/raspbian/)

# 开启SSH连接

在boot目录下新建一个ssh空文件即可

# 设置wifi连接

与上面类似，在其目录下新建一个WiFi配置文件`wpa_supplicant.conf`，似乎只有新系统用
```
country=CN
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="你的wifi名"
    psk="wifi密码"
    key_mgmt=WPA-PSK
    priority=1
}
```

# 设置中文字体

系统默认英文，可以通过`sudo raspi-config`来配置中文字体，这样SSH显示了中文字体，树莓派连屏幕的终端还是乱码。

`sudo apt instll fonts-wqy-zenhei`

# 更正时区

`sudo dpkg-reconfigure tzdata`选择亚洲、上海即可

# 挂载硬盘

发现一个问题，当设置自动挂载硬盘后，不安硬盘的情况下就无法正常开机。

# 更换国内源

deb http://mirrors.aliyun.com/raspbian/raspbian/ jessie main non-freecontrib
deb-src http://mirrors.aliyun.com/raspbian/raspbian/ jessie mainnon-free contrib

## 创建git服务器

一，创建一个用户，因为有pi用户了，创不创无所谓。

二，创建一个裸仓库
sudo git init --bare bin.git

公钥放到.ssh里面

OK了

三，在工作机上 
git clone pi@ip:<路径>/bin.git

剩下的就是不断的推送了，出于安全还可以设置git不能登录shell

## 使用树莓派搭建VPN

http://haipeng.me/2017/12/12/raspberry-pi-vpn-remote-access/