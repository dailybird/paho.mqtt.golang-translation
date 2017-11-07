# Client 及相关方法

### type Client

```
type Client interface {
    IsConnected() bool
    Connect() Token
    Disconnect(quiesce uint)
    Publish(topic string, qos byte, retained bool, payload interface{}) Token
    Subscribe(topic string, qos byte, callback MessageHandler) Token
    SubscribeMultiple(filters map[string]byte, callback MessageHandler) Token
    Unsubscribe(topics ...string) Token
    AddRoute(topic string, callback MessageHandler)
}
```

`Client` 是 `paho.mqtt.golang` 中的一个客户端接口定义，主要用于进行模拟测试。

> Client is the interface definition for a Client as used by this library, the interface is primarily to allow mocking tests.

该客户端基于MQTT v3.1.1 版本，用以与 MQTT 服务器进行非阻塞的通信，并可以在后台运行。应用可以通过以下方式连接到 MQTT 服务器：

> It is an MQTT v3.1.1 client for communicating with an MQTT server using non-blocking methods that allow work to be done in the background. An application may connect to an MQTT server using:

```
纯 TCP socket
安全的 SSL/TLS socket
websocket

A plain TCP socket
A secure SSL/TLS socket
A websocket
```

为了确保 MQTT 定义中的服务质量 （ Qos ）能够得到有效的保障，我们需要使用消息的持久化机制。而这一点，是通过提供一个实现了 Store 接口的类型而实现的。方便起见，`paho.mqtt.golang` 中已经提供了两个足够适用于大多数场景的 `Store` 实现：`FileStore` 与 `MemoryStore`。大家可以再对应的文档中找到更多的信息。更多的连接选项可以通过配置和应用 `ClientOptions` 类型来指定。

> To enable ensured message delivery at Quality of Service \(QoS\) levels described in the MQTT spec, a message persistence mechanism must be used. This is done by providing a type which implements the Store interface. For convenience, FileStore and MemoryStore are provided implementations that should be sufficient for most use cases. More information can be found in their respective documentation. Numerous connection options may be specified by configuring a and then supplying a ClientOptions type.

### func NewClient

```
func NewClient(o *ClientOptions) Client
```

我们可以通过 `NewClient` 方法创建一个 MQTT v3.1.1 的客户端，该方法接受一个 `ClientOptions` 类型的参数用于提供与连接有关的配置。在这一 `Client` 使用之前，需要最先调用 `Client` 的 `Connect` 方法。这是因为，在应用准备好之前，必须确保相关的资源都已经被创建了。（译注：即我们要想使用 MQTT 中客户端的功能：如注册、发布等，必须事先调用 `Client` 的  `Connect` 方法。）

> NewClient will create an MQTT v3.1.1 client with all of the options specified in the provided ClientOptions. The client must have the Connect method called on it before it may be used. This is to make sure resources \(such as a net connection\) are created before the application is actually ready.



