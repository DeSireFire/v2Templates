
自整理自用v2ray配置文件模板
=======
[![Packagist](https://img.shields.io/packagist/l/doctrine/orm.svg)](https://github.com/jhao104/proxy_pool/blob/master/LICENSE)


### 介绍
鉴于找了很多v2ray的多用户管理都没达到自己的需求。  
于是,挽起袖子。“闪开，我自己来！”  
该repo先整理一下自己要用到的json模板。

### Json注释

#### base.json 基础配置

* log: 日志配置，表示 V2Ray 如何输出日志。
* api: 内置的远程控置 API。
* dns: 内置的 DNS 服务器，若此项不存在，则默认使用本机的 DNS 设置。
* stats: 当此项存在时，开启统计信息。
* routing: 路由配置。
* policy: 本地策略可进行一些权限相关的配置。
* reverse: 反向代理配置。
* inbounds: 一个数组，每个元素是一个入站连接配置。
* outbounds: 一个数组，每个元素是一个出站连接配置。列表中的第一个元素作为主出站协议。当路由匹配不存在或没有匹配成功时，流量由主出站协议发出。
* transport: 用于配置 V2Ray 如何与其它服务器建立和使用网络连接。

#### log.json 日志配置

* access: 访问日志文本保存的路径。
* error: 错误日志文本保存的路径。
* loglevel: 日志记录等级[info，warning，...]。

#### inbounds 入站配置 

1. vmessUser.json 用户设置
* protocol: 主传入协议。
* port: 服务器监听端口。
* settings: 设置。
* streamSettings: 更多设置。
* sniffing: 不懂是什么鬼。
* clients: 链接设置。
* id: 用户ID(UUID)，客户端连接使用，必须保持一致。
* level: 不知道什么等级，默认1。
* alterId: 使用的alterID数量（越大越不容易被识别，但消耗越大），推荐16，一般使用64足够，也需要客服双端保持一致。
* network: 链接方式[kcp,ws,...]。
* email: 用户邮箱地址，用于区分不同用户的流量。
* id: 。