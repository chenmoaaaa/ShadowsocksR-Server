
1.安装服务
方法一:
    我的vps是在搬瓦工上的,在它KiwiVM管理端提供了一个一键安装的快捷操作,因此十分方便.
    它的原理应该是直接是源码编译安装:源码安装包shadowsocksr.tar.gz我已放在Software目录下,感兴趣的同学可以自行研究

方法二:
    pip 安装 # pip install shadowsocks
    参考: https://github.com/shadowsocks/shadowsocks/wiki/Shadowsocks-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E

2.修改配置文件
    默认配置文件会在/etc/shadowsocks.json
    {
        "server":"my_server_ip",
        "server_port":8388,
        "local_address": "127.0.0.1",
        "local_port":1080,
        "password":"myPassword",
        "timeout":300,
        "method":"aes-256-cfb",
        "fast_open": false
    }
    相关配置说明:
    参考: https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File
    | Name          | Explanation                                     |
    | ------------- | ----------------------------------------------- |
    | server        | the address your server listens                 |
    | server_port   | server port                                     |
    | local_address | the address your local listens                  |
    | local_port    | local port                                      |
    | password      | password used for encryption                    |
    | timeout       | in seconds                                      |
    | method        | default: "aes-256-cfb", see [Encryption]        |
    | fast_open     | use [TCP_FASTOPEN], true / false                |
    | workers       | number of workers, available on Unix/Linux      |

3.服务运行
    i.启动port=443
    python /shadowsocksr/shadowsocks/server.py -s ::0 -o tls1.2_ticket_auth_compatible -p `cat /root/.kiwivm-shadowsocksr-port` -k `cat /root/.kiwivm-shadowsocksr-password` -m `cat /root/.kiwivm-shadowsocksr-encryption` --user nobody --workers 2 -d start
    ii.服务启动:
    ssserver -c /etc/shadowsocks.json   #命令行启动
    ssserver -c /etc/shadowsocks.json -d start  #后台启动
    ssserver -c /etc/shadowsocks.json -d stop
    ssserver -c /etc/shadowsocks.json -d restart
    iii.自启动
    echo 'ssserver -c /etc/shadowsocks.json -d start' >> /etc/rc.local

