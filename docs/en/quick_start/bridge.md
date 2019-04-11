# Data synchronization

During data synchronization,  MQTT protocol is used to establish bidirectional synchronous connection between Edge (local) and other central nodes (remote). The central nodes can be private deployed EMQ X, public cloud AWS IoT, Azure IoT Hub and other MQTT protocol access points.   

Data synchronization realized bidirectional synchronization by forward and subscription :

- Forward: Forward one or more local topics to the corresponding remote topic, realizing  **local -> remote**  synchronization
- Subscription: Subscribe to one or more remote topics and republish the data locally

-  Mountpoint (optional): Configure the prefix for forwarding topics uniformly



###  Examples of data synchronization rule

Forward： `sersor1/#` ，`sensor2/#`

Subscription：`cmd/topic1`

Mountpoint: `emqx_edge/`

The rule is applied as follows:：

- If the messages received by the local Edge matche the subject sersor1/#, sensor2/#, these messages will be forwarded to the remote node by **mountpoint:**

  ```bash
  sersor1/1 -> emqx_edge/sersor1/1
  ```

- If the remote server receives a cmd/topic1 topic message, it will publish a message with the same topic at the local Edge.

