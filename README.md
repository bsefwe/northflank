# 使用 northflank 部署 Xray 高性能代理服务，通过 Vless + WS + Tls 协议传输，并配置 Web 网站。

> 提醒： 滥用可能导致账户被BAN！！！

## 概述

每次部署自动选择最新的 Alpine Linux 和 Xray-core 。

可通过自定义网络配置文件启动 Xray 和 Caddy，按需配置各种功能。

  * 务必替换部署时的默认 UUID。
  * start.sh文件里修改UUID和伪装网站。
  * northflank账号需要绑定信用卡，可以搭建两个免费服务。
## 镜像

注册网站

[![Deploy](https://app.northflank.com/deploy/gfujrf.png)](https://app.northflank.com) 




## 流量中转

  <summary>可以使用 Cloudflare 的 Workers 来中转流量，配置为：</summary>
  
  ```js
  const SingleDay = 'xxx.herokuapp.com';
  const DoubleDay = 'xxx.herokuapp.com';
  addEventListener(
      "fetch", event => {
          let nd = new Date();
          if (nd.getDate() % 2) {
              host = SingleDay;
          } else {
              host = DoubleDay;
          }
          let url = new URL(event.request.url);
          url.hostname = host;
          let request = new Request(url, event.request);
          event.respondWith(
              fetch(request)
          )
      }
  )
  ```

## Xray 默认配置

  ```bash
    * 协议：Vless/vmess
    * 地址：XXX--XXX--4h6hhh7t7x5j.code.run
    * 端口：443
    * 默认UUID：5aaed9b7-7fe3-47c3-bb52-db59859ce198
    * 加密：none
    * 传输协议：ws
    * 伪装类型：none
    * 伪装域名：
    * 路径：/api-vless 或 /api-vmess
    * 底层传输安全：tls
    * 跳过证书验证：false
    * SNI：XXX--XXX--4h6hhh7t7x5j.code.run
  ```
