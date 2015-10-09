gShadowsocks客戶端
===========

當前版本: 1.5.0
[![Build Status](https://travis-ci.org/clowwindy/shadowsocks-nodejs.png)](https://travis-ci.org/clowwindy/shadowsocks-nodejs)

gShadowsocks是一個可以帶你穿過防火牆的輕量代理軟件 基於nodejs版本的  [shadowsocks](https://github.com/shadowsocks/shadowsocks-nodejs).

TCP和UDP都是可以實現的

其他平臺shadowsocks的客戶端可以在 [這裏](https://github.com/clowwindy/shadowsocks/wiki/Ports-and-Clients) 找到.

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
