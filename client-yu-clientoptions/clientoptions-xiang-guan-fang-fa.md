# ClientOptions 相关方法

### func \(\*ClientOptions\) AddBroker

```
func (o *ClientOptions) AddBroker(server string) *ClientOptions.
```

`AddBroker` 可以为此客户端添加一个需要连接的代理。`AddBroker` 的参数格式为 `scheme://host:port`。其中，`scheme` 可以使 `tcp`，`ssl`，`ws` 中的一种；`host` 为代理的 IP 地址或域名；`port` 为代理监听的端口号。

> AddBroker adds a broker URI to the list of brokers to be used. The format should be scheme://host:port Where "scheme" is one of "tcp", "ssl", or "ws", "host" is the ip-address \(or hostname\) and "port" is the port on which the broker is accepting connections.

func \(\*ClientOptions\) SetAutoReconnect

```
func (o *ClientOptions) SetAutoReconnect(a bool) *ClientOptions.
```

`SetAutoReconnect` 会设置连接丢失后重连逻辑是否启用。而这一机制的启用与否并不会影响 `ConnectionLostHandler` （译注：失去连接事件的回调）回调的执行。

> SetAutoReconnect sets whether the automatic reconnection logic should be used when the connection is lost, even if disabled the ConnectionLostHandler is still called

### func \(\*ClientOptions\) SetBinaryWill

```
func (o *ClientOptions) SetBinaryWill(topic string, payload []byte, qos byte, retained bool) *ClientOptions
```

SetBinaryWill 会设置一条遗嘱消息。当客户端连接（到代理）时，这条消息将会发送给代理。参数中提供了 topic，用于在之后将该消息推送给所有订阅了该 topic 的客户端。

> SetBinaryWill accepts a \[\]byte will message to be set. When the client connects, it will give this will message to the broker, which will then publish the provided payload \(the will\) to any clients that are subscribed to the provided topic.

译注：这里文档中的表述有些歧义，遗嘱消息的发送时机是连接异常终止。大家可以参考链接 [https://www.oschina.net/question/69055\_125109](https://www.oschina.net/question/69055_125109)

以下为摘录：

> will topic 和 will message 有点像立遗嘱。也即在连接服务器时通告：当我连接异常终止时请帮我发布这条 message 到相应的 topic。但要注意的是，will topic 和 will message 必须成对出现，并且还须设置 will flag。如果需要服务器保留这份遗嘱，则还需设置 will retain。

### func \(\*ClientOptions\) SetCleanSession

```
func (o *ClientOptions) SetCleanSession(clean bool) *ClientOptions
```

SetCleanSession 方法会设置连接消息（ CONNECT Message ）中的 clean session 标识位。当设置这一标识位时，所有在代理中保存但尚未发送给客户端的消息都不会再发送。且客户端只有断开并重连代理之后才能继续发送消息。

> SetCleanSession will set the "clean session" flag in the connect message when this client connects to an MQTT broker. By setting this flag, you are indicating that no messages saved by the broker for this client should be delivered. Any messages that were going to be sent by this client before disconnecting previously but didn't will not be sent upon connecting to the broker.

译注：这里文档的表述比较绕，大家可以参考以下链接：[http://topmanopensource.iteye.com/blog/1700431/](http://topmanopensource.iteye.com/blog/1700431/)，[https://github.com/mcxiaoke/mqtt/blob/master/mqtt/0301-CONNECT.md\#连接标志-connect-flags](https://github.com/mcxiaoke/mqtt/blob/master/mqtt/0301-CONNECT.md#连接标志-connect-flags)

以下为一些摘录：

> 一般来说，客户端连接时总是将清理会话标志设置为0或1，并且不交替使用两种值。这个选择取决于具体的应用。清理会话标志设置为1的客户端不会收到旧的应用消息，而且在每次连接成功后都需要重新订阅任何相关的主题。清理会话标志设置为0的客户端会收到所有在它连接断开期间发布的QoS 1和QoS 2级别的消息。因此，要确保不丢失连接断开期间的消息，需要使用QoS 1或 QoS 2级别，同时将清理会话标志设置为0。

> 在连接之前，您必须设置 cleanSession 方式；在整个会话期间都将保持此方式。要更改此属性的设置，必须将客户机断开连接，然后再重新连接客户机。如果您将方式从使用 cleanSession=false 更改为 cleanSession=true，那么此客户机先前的所有预订以及尚未接收到的任何发布都将被废弃。





