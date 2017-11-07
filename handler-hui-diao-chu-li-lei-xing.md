# Handler 处理器

译注：处理器类型（或文档中所说的回调类型）用于创建一个相应的处理器，可以在设置后，作为指定事件发生后的处理函数。用法如下（例子来源于`paho.mqtt.golang` 的实例代码）：

```
var f mqtt.MessageHandler = func(client mqtt.Client, msg mqtt.Message) {
	fmt.Printf("TOPIC: %s\n", msg.Topic())
	fmt.Printf("MSG: %s\n", msg.Payload())
}

opts := mqtt.NewClientOptions()

opts.SetDefaultPublishHandler(f)
```

### func DefaultConnectionLostHandler

```
func DefaultConnectionLostHandler(client Client, reason error)
```

`DefaultConnectionLostHandler` 是一个方法定义，用于简单的汇报客户端失去连接的 DEBUG 日志。

> DefaultConnectionLostHandler is a definition of a function that simply reports to the DEBUG log the reason for the client losing a connection.

### type ConnectionLostHandler

```
type ConnectionLostHandler func(Client, error)
```

`ConnectionLostHandler` 是一个回调类型，会在与 MQTT 代理发生非预期的连接中断后执行。由于调用 `Disconnect` 或 `ForceDisconnect` 方法而导致的连接中断不会触发这一回调。

> ConnectionLostHandler is a callback type which can be set to be executed upon an unintended disconnection from the MQTT broker. Disconnects caused by calling Disconnect or ForceDisconnect will not cause an OnConnectionLost callback to execute.

### type MessageHandler

```
type MessageHandler func(Client, Message)
```

`MessageHandler` 是一个回调类型，用于在收到订阅的 `Topic` 发布的消息时触发。

> MessageHandler is a callback type which can be set to be executed upon the arrival of messages published to topics to which the client is subscribed.

### type OnConnectHandler

```
type OnConnectHandler func(Client)
```

OnConnectHandler 是一个回调类型，用于在客户端状态由「未连接」/「断开连接」转换为「已连接」状态时触发，二者分别对应于初始化连接和重连。

> OnConnectHandler is a callback that is called when the client state changes from unconnected/disconnected to connected. Both at initial connection and on reconnection.



