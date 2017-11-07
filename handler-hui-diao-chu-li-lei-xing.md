# Handler 处理器

### func DefaultConnectionLostHandler

```
func DefaultConnectionLostHandler(client Client, reason error)
```

> DefaultConnectionLostHandler is a definition of a function that simply reports to the DEBUG log the reason for the client losing a connection.

### type ConnectionLostHandler

```
type ConnectionLostHandler func(Client, error)
```

> ConnectionLostHandler is a callback type which can be set to be executed upon an unintended disconnection from the MQTT broker. Disconnects caused by calling Disconnect or ForceDisconnect will not cause an OnConnectionLost callback to execute.

### type MessageHandler

```
type MessageHandler func(Client, Message)
```

> MessageHandler is a callback type which can be set to be executed upon the arrival of messages published to topics to which the client is subscribed.

### type OnConnectHandler

```
type OnConnectHandler func(Client)
```

> OnConnectHandler is a callback that is called when the client state changes from unconnected/disconnected to connected. Both at initial connection and on reconnection



