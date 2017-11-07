# ClientOptions 及其创建方法

```
type ClientOptions struct {
    Servers         []*url.URL
    ClientID        string
    Username        string
    Password        string
    CleanSession    bool
    Order           bool
    WillEnabled     bool
    WillTopic       string
    WillPayload     []byte
    WillQos         byte
    WillRetained    bool
    ProtocolVersion uint

    TLSConfig             tls.Config
    KeepAlive             int64
    PingTimeout           time.Duration
    ConnectTimeout        time.Duration
    MaxReconnectInterval  time.Duration
    AutoReconnect         bool
    Store                 Store
    DefaultPublishHandler MessageHandler
    OnConnect             OnConnectHandler
    OnConnectionLost      ConnectionLostHandler
    WriteTimeout          time.Duration
    MessageChannelDepth   uint
    // contains filtered or unexported fields
}
```

`ClientOptions` 包含客户端的配置选项。

> ClientOptions contains configurable options for an Client.

### func NewClientOptions

```
func NewClientOptions() *ClientOptions
```

`NewClientOptions` 方法将会创建一个 `ClientOptions` 对象，该对象会附带一些默认的配置。

> NewClientOptions will create a new ClientClientOptions type with some default values.

```
Port: 1883
CleanSession: True
Order: True
KeepAlive: 30 (seconds)
ConnectTimeout: 30 (seconds)
MaxReconnectInterval 10 (minutes)
AutoReconnect: True
```



