
## 注意本项目有封号的风险，不要用常用的github账号

## 概述

### 注册地址：https://okteto.com/
本专案用于在 Okteto上部署 xRay WebSocket，

部署完成后，每次启动应用时，运行的 XRay 将始终为最新版本


## X 默认配置
  ```bash
    * 协议：Vless
    * 地址：自选 IP
    * 端口：443
    * 默认UUID：ad806487-2d26-4636-98b6-ab85cc8521f7
    * 加密：none
    * 传输协议：ws
    * 伪装类型：none
    * 伪装域名：xxx.workers.dev (Cloudflare Workers 反代地址)
    * 路径：/
    * 底层传输安全：tls
    * 跳过证书验证：false
    * SNI：xxx.workers.dev (Cloudflare Workers 反代地址)

## 接入 CloudFlare

以下两种方式均可以将应用接入 CloudFlare，从而在一定程度上提升速度。

 1. 为应用绑定域名，并将该域名接入 CloudFlare
 2. 通过 CloudFlare Workers 反向代理


