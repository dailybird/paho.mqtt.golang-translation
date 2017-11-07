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

> Message defines the externals that a message implementation must support these are received messages that are passed to the callbacks, not internal messages.





