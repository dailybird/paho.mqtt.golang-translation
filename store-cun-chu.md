# Store 存储

### type Store

```
type Store interface {
    Open()
    Put(key string, message packets.ControlPacket)
    Get(key string) packets.ControlPacket
    All() []string
    Del(key string)
    Close()
    Reset()
}
```

Store 是一个接口，用于提供消息的持久化。由于可能不得不使用相同的消息 ID 存储不同的消息，我们需要为每一个消息提供不同的键值。比如加上 `i.` 或 `o.` 前缀。

> Store is an interface which can be used to provide implementations for message persistence. Because we may have to store distinct messages with the same message ID, we need a unique key for each message. This is possible by prepending "i." or "o." to each message id.



