# 数据同步

数据同步使用 MQTT 协议建立 Edge （本地）到其他中心节点（远程）的双向同步连接，中心节点可以是 私有部署的 EMQ X，公有云 AWS IoT、Azure IoT Hub 等 MQTT 协议接入点。

数据同步使用转发（forward）与订阅主题（subscription）来实现双向同步：

- 转发：将本地一个或多个主题转发至远程对应的主题，实现 **本地 --> 远程** 同步
- 订阅主题：订阅远程的一个或多个主题并将数据重新在本地发布

- 挂载点(mountpoint，可选)：配置转发主题统一加上的前缀



### 数据同步规则示例

转发主题： `sersor1/#` ，`sensor2/#`

订阅主题：`cmd/topic1`

挂载点为 `emqx_edge/`

则该规则应用如下：

- 本地 Edge 接收到的消息如果匹配主题 sersor1/#，sensor2/#，这些消息会被**加上挂载点**转发到远程节点上：

  ```bash
  sersor1/1 -> emqx_edge/sersor1/1
  ```

- 远程服务器如果收到 cmd/topic1 主题消息，将在本地 Edge 相同主题发布消息。

