# ClientOptionsReader 及相关方法

### type ClientOptionsReader

```
type ClientOptionsReader struct {

    // contains filtered or unexported fields

}
```

`ClientOptionsReader` 提供了 `ClientOptions` 在被初始化之后，用以访问其中配置的接口。（译注：`ClientOptions` 已经实现了这一接口，即可以直接在 `ClientOptions` 对象中使用以下方法读取配置。）

> ClientOptionsReader provides an interface for reading ClientOptions after the client has been initialized.

### func \(\*ClientOptionsReader\) AutoReconnect

```
func (r *ClientOptionsReader) AutoReconnect() bool
```

### func \(\*ClientOptionsReader\) CleanSession

```
func (r *ClientOptionsReader) CleanSession() bool
```

`CleanSession` 会返回 `clean session` 标识位是否被设置。

> CleanSession returns whether Cleansession is set.

### func \(\*ClientOptionsReader\) ClientID

```
func (r *ClientOptionsReader) ClientID() string
```

`ClientID` 会返回设置的客户端 ID 值。

> ClientID returns the set client id.

### func \(\*ClientOptionsReader\) ConnectTimeout

```
func (r *ClientOptionsReader) ConnectTimeout() time.Duration
```

### func \(\*ClientOptionsReader\) KeepAlive

```
func (r *ClientOptionsReader) KeepAlive() time.Duration
```

### func \(\*ClientOptionsReader\) MaxReconnectInterval

```
func (r *ClientOptionsReader) MaxReconnectInterval() time.Duration
```

### func \(\*ClientOptionsReader\) MessageChannelDepth

```
func (r *ClientOptionsReader) MessageChannelDepth() uint
```

### func \(\*ClientOptionsReader\) Order

```
func (r *ClientOptionsReader) Order() bool
```

### func \(\*ClientOptionsReader\) Password

```
func (r *ClientOptionsReader) Password() string
```

`Password` 会返回设置的密码。

> Password returns the set password

### func \(\*ClientOptionsReader\) PingTimeout

```
func (r *ClientOptionsReader) PingTimeout() time.Duration
```

### func \(\*ClientOptionsReader\) ProtocolVersion

```
func (r *ClientOptionsReader) ProtocolVersion() uint
```

### func \(\*ClientOptionsReader\) Servers

```
func (r *ClientOptionsReader) Servers() []*url.URL
```

Servers returns a slice of the servers defined in the clientoptions

### func \(\*ClientOptionsReader\) TLSConfig

```
func (r *ClientOptionsReader) TLSConfig() tls.Config
```

### func \(\*ClientOptionsReader\) Username

```
func (r *ClientOptionsReader) Username() string
```

`Username` 会返回设置的用户名。

> Username returns the set username

### func \(\*ClientOptionsReader\) WillEnabled

```
func (r *ClientOptionsReader) WillEnabled() bool
```

### func \(\*ClientOptionsReader\) WillPayload

```
func (r *ClientOptionsReader) WillPayload() []byte
```

### func \(\*ClientOptionsReader\) WillQos

```
func (r *ClientOptionsReader) WillQos() byte
```

### func \(\*ClientOptionsReader\) WillRetained

```
func (r *ClientOptionsReader) WillRetained() bool
```

### func \(\*ClientOptionsReader\) WillTopic

```
func (r *ClientOptionsReader) WillTopic() string
```

### func \(\*ClientOptionsReader\) WriteTimeout

```
func (r *ClientOptionsReader) WriteTimeout() time.Duration
```



