# Message 消息

### type Message

```
type Message interface {
    Duplicate() bool
    Qos() byte
    Retained() bool
    Topic() string
    MessageID() uint16
    Payload() []byte
}
```

`Message` 定义了消息实现必须支持的外部环境。以上消息指定是会触发回调的接收消息，而不是内部消息。

> Message defines the externals that a message implementation must support these are received messages that are passed to the callbacks, not internal messages.



