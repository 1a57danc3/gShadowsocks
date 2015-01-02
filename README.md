gShadowsocks客户端
===========

当前版本: 1.5.0
[![Build Status](https://travis-ci.org/clowwindy/shadowsocks-nodejs.png)](https://travis-ci.org/clowwindy/shadowsocks-nodejs)

gShadowsocks是一个可以带你穿过防火墙的轻量代理软件 基于nodejs版本的  [shadowsocks](https://github.com/shadowsocks/shadowsocks-nodejs).

TCP和UDP都是可以实现的

其他平台shadowsocks的客户端可以在 [这里](https://github.com/clowwindy/shadowsocks/wiki/Ports-and-Clients) 找到.

客户端使用方法
-----------

下载最新的gShadowsocks

修改 `config.json` 这个文件 （Windows下面最好使用notepad++修改，使用系统自带文本编辑器可能会丢失格式）

    {
        "server":"my_server_ip",
        "server_port":8388,
        "local_port":1080,
        "password":"barfoo!",
        "timeout":600,
        "method":"table"
    }

参数字段说明:

    server          你的服务器IP (IPv4/IPv6), 注意 这是服务器的外网独立IP
    server_port     服务器监听端口
    local_port      本地监听端口
    password        你所设置的密码
    timeout         超时时间设置
    method          加密方式 如： "bf-cfb", "aes-256-cfb", "des-cfb", "rc4", 等等. 默认是 table


修改配置文件完成后 运行`gShadowsocks.exe`.

然后改变您的浏览器代理端口 详见http://ippotsuko.lofter.com/post/15c52d_156fc15

    protocol: socks5
    hostname: 127.0.0.1
    port:     your local_port


服务器端使用说明：

打开根目录修改 `config.json`. 然后在你拥有公网独立IP的服务器上运行 `gShadowsocksserver.exe`


进阶使用 懒得翻译了自己看吧
------------

You can use args to override settings from `config.json`.

    sslocal -s server_name -p server_port -l local_port -k password -m bf-cfb
    ssserver -p server_port -k password -m bf-cfb
    ssserver -c /etc/shadowsocks/config.json

Example of multi-user server support can be found in `test/config-multi-passwd.json`.

开发
-----------------------------

你可以构建 coffee source 代码以及测试:

    npm install -g coffee-script
    cake build test

许可开源协议License
-----------------
MIT

错误和问题
----------------
请访问 [issue tracker](https://github.com/clowwindy/shadowsocks-nodejs/issues?state=open)

Mailing list: http://groups.google.com/group/shadowsocks

Also see [troubleshooting](https://github.com/clowwindy/shadowsocks/wiki/Troubleshooting)



启动器来自:goagent-taskbar https://github.com/goagent/taskbar

购买高速shadowsocks服务  尽在静云 Jingyun.org    Copyleft 2014

使用静云，即可在中国的各个角落，尽情享受自由的网络世界
无论是电脑还是手机，也不管是Wi-Fi或是移动网络

静云都能始终伴随你左右。
