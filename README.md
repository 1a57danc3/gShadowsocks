gShadowsocks客戶端 基於shadowsocks-nodejs 和 goagent-taskbar
===========

當前版本: 1.5.3

gShadowsocks 是一個可以帶你穿過防火牆的輕量代理軟件 基於nodejs版本的  [shadowsocks](https://github.com/shadowsocks/shadowsocks-nodejs).

TCP和UDP都是可以實現的

**本項目不再更新; 請使用 [其他版本](https://github.com/clowwindy/shadowsocks/wiki/Ports-and-Clients).**


客戶端使用方法
-----------

下載最新的gShadowsocks

修改 `config.json` 這個文件 （Windows下面最好使用notepad++修改，使用系統自帶文本編輯器可能會丟失格式）

    {
        "server":"my_server_ip",
        "server_port":8388,
        "local_port":1080,
        "password":"barfoo!",
        "timeout":600,
        "method":"table"
    }

參數字段說明:

    server          你的服務器IP (IPv4/IPv6), 注意 這是服務器的外網獨立IP
    server_port     服務器監聽端口
    local_port      本地監聽端口
    password        你所設置的密碼
    timeout         超時時間設置
    method          加密方式 如： "bf-cfb", "aes-256-cfb", "des-cfb", "rc4", 等等. 默認是 table


修改配置文件完成後 運行`gShadowsocks.exe`.

然後改變您的瀏覽器代理端口 詳見http://ippotsuko.lofter.com/post/15c52d_156fc15

    protocol: socks5
    hostname: 127.0.0.1
    port:     your local_port


服務器端使用說明：

打開根目錄修改 `config.json`. 然後在你擁有公網獨立IP的服務器上運行 `gShadowsocksserver.exe`


進階使用 懶得翻譯了自己看吧
------------

You can use args to override settings from `config.json`.

    sslocal -s server_name -p server_port -l local_port -k password -m bf-cfb
    ssserver -p server_port -k password -m bf-cfb
    ssserver -c /etc/shadowsocks/config.json

Example of multi-user server support can be found in `test/config-multi-passwd.json`.

開發
-----------------------------

你可以構建 coffee source 代碼以及測試:

    npm install -g coffee-script
    cake build test

許可開源協議License
-----------------
MIT

錯誤和問題
----------------
請訪問 [issue tracker](https://github.com/clowwindy/shadowsocks-nodejs/issues?state=open)

Mailing list: http://groups.google.com/group/shadowsocks

Also see [troubleshooting](https://github.com/clowwindy/shadowsocks/wiki/Troubleshooting)



啓動器來自:goagent-taskbar https://github.com/goagent/taskbar

下載 https://github.com/goagent/taskbar/archive/master.zip
然後用 vc6 打開 taskbar.dsw, 點"編譯"得到 taskbar.exe
此時的 taskbar.exe 是 cmd.exe 的一個外殼
用 reshack/exesope 修改 taskbar.exe 的圖標資源和字符串資源就能得到自定義的任意 console 程序的外殼了
比如 goagent.exe

更多**程式可以見 https://github.com/fqtools

----------

gShadowsocks based on shadowsocks-nodejs and goagent-taskbar
==================

shadowsocks-nodejs

[![NPM version]][NPM] [![Build Status]][Travis CI]

shadowsocks-nodejs is a node.js port of [shadowsocks].

**Deprecated; please use [Other versions].**

Many people are asking why. Here's why.

- https://github.com/clowwindy/shadowsocks-nodejs/issues/35
- https://github.com/joyent/node/issues/5949

The GC of node.js sucks.

Python version [handles 5000 connections with 50MB RAM](https://github.com/clowwindy/shadowsocks/wiki/Optimizing-Shadowsocks) while node.js version
handles 100 connections with 300MB RAM. Why should we continue to support
node.js?


[Build Status]:    https://img.shields.io/travis/clowwindy/shadowsocks-nodejs/master.svg?style=flat
[NPM]:             https://www.npmjs.org/package/shadowsocks
[NPM version]:     https://img.shields.io/npm/v/shadowsocks.svg?style=flatp
[Travis CI]:       https://travis-ci.org/clowwindy/shadowsocks-nodejs
[shadowsocks]:     https://github.com/clowwindy/shadowsocks
[Other versions]:  https://github.com/clowwindy/shadowsocks/wiki/Ports-and-Clients

MIT License and Thx for anthor clowwindy
-------
goagent-taskbar

Download https://github.com/goagent/taskbar/archive/master.zip

Open taskbar.dsw with vc6/visual studio , run and build it that you can get taskbar.exe

taskbar.exe is one of the shell of cmd.exe now

You can use reshack/exesope to edit 'icon' or 'string' resource of taskbar.exe and you can get any shell of console

such as goagent.exe

No License and Thx for anthor phuslu


------

More Anti-Gre@tFirewall Tools on https://github.com/fqtools
