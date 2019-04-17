# EMQ X Edge 边缘消息服务器

## 简介

*EMQ X Edge* 是轻量级开源消息服务器，可运行在资源受限的边缘设备上。它是连接云端和本地设备之间的桥梁，作为物联网平台体系中的边缘计算节点上运行的消息代理，在边缘节点上使用业务规则引擎将大部分数据进行本地处理，也能够实时响应设备端的请求。在EMQ X边缘节点与后台的EMQ X服务器处理集群之间采用加密的传输协议，如果Edge节点和远程EMQ之间由于传输网络问题导致连接断开，Edge节点会自动保存指定的消息到本地的存储，并且在网络正常之后会自动将数据发送到远程的 EMQ X 集群、其他 MQTT 消息服务器。


*EMQ X Edge* 完整支持 MQTT V3.1/V3.1.1/V5.0 版本协议规范，并支持 MQTT-SN 、TCP、WebSocket、CoAP、Stomp，以及 Modbus 等工业协议。


<img src="./_assets/edge.png" class="medium-size"/>


## 安装使用

下载地址: [https://www.emqx.io/downloads/emq/edge](https://www.emqx.io/downloads/emq/edge)

使用文档: [https://developer.emqx.io/docs/edge/v3/cn/](https://developer.emqx.io/docs/edge/v3/cn/)
