# GUILD

> run on mac m1

1. 下载 openresty, 置于根目录

- 执行 ./configure
  > 注意修改 brew 安装后修改根目录, 参考https://github.com/bingoohuang/blog/issues/63

```sh
alias telnet="/opt/homebrew/Cellar/telnet/63/bin/telnet"
export PCRE_HOME=/opt/homebrew/Cellar/pcre/8.44
export OPENSSL_HOME=/opt/homebrew/Cellar/openssl@1.1/1.1.1j
```

2. 运行 nginx

```sh
./www/run.sh start
```

3. 安装 wireshark 监听 loopback（127.0.0.1)，过滤 80 端口
   > filter 栏过滤 80 端口

```
tcp.port==80
```

4. telnet

```sh
telnet

open www.chrono.com 80

# press ctrl + ] ; press enter

# into edit mode

GET /16-1 HTTP/1.1
Host: www.chrono.com
```
