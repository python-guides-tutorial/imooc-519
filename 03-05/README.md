# 3-5 用squid自建代理服务（1）

|本期版本|上期版本
|:---:|:---:
`Mon Sep 25 15:38:34 CST 2023` | -


## example


```
acl SSL_ports port 443
acl Safe_ports port 80    # http
acl Safe_ports port 443    # https
acl CONNECT method CONNECT
http_access allow all
http_port 3128
visible_hostname proxy
```


## macOS


```bash
ls -al /usr/local/etc | grep squid.conf
```

```bash
export https_proxy=http://127.0.0.1:3128 http_proxy=http://127.0.0.1:3128 all_proxy=socks5://127.0.0.1:3128
curl  https://www.hawu.me/operation/852
```


## Ref

* <https://termius.com/> 
* [使用squid搭建代理服务器](https://www.hawu.me/operation/852)
* [squid：http和https的代理服务器设置指南(MacOS版）](https://blog.csdn.net/liumiaocn/article/details/108629944)