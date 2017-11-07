# 其他

### type MId

```
type MId uint16
```

MId 是在 MQTT 标准中指定的 16 比特的消息 ID。大体上说，客户端应用不应依赖于这些值。

> MId is 16 bit message id as specified by the MQTT spec. In general, these values should not be depended upon by the client application.

### type PacketAndToken

```
type PacketAndToken struct {
    // contains filtered or unexported fields
}
```

> PacketAndToken is a struct that contains both a ControlPacket and a Token. This struct is passed via channels between the client interface code and the underlying code responsible for sending and receiving MQTT messages.



