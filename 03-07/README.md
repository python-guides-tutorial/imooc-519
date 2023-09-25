# 3-7 创建加密的squid代理服务（3）

|本期版本|上期版本
|:---:|:---:
`Mon Sep 25 15:54:38 CST 2023` | -

```bash
# htpasswd

apt-get install apach2-utils
```


```bash
htpasswd -c squid_pass <username>
```


```bash
export https_proxy=http://username:password@127.0.0.1:3128
```

**认证配置**

```
auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/squid_passwd
acl nesa_users proxy_auth REQUIRED
http_access allow ncsa_users
```


## Ref

* [五大开源 Web 代理服务器横评：Squid、Privoxy、Varnish、Polipo、](https://linux.cn/article-7119-1.html)