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

> Store is an interface which can be used to provide implementations for message persistence. Because we may have to store distinct messages with the same message ID, we need a unique key for each message. This is possible by prepending "i." or "o." to each message id.



