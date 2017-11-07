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

ClientOptions 包含客户端的配置选项。

