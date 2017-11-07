# 变量

```
var (
    ERROR    *log.Logger
    CRITICAL *log.Logger
    WARN     *log.Logger
    DEBUG    *log.Logger
)
```

作为内置的输出库，默认情况下，在不对其进行配置时，`paho.mqtt.golang`是不会进行输出打印的。但开发者可以自行配置他们。（译注：比如，`mqtt.DEBUG = log.New(os.Stdout, "", 0)`可以使 `DEBUG` 级别的内容输出。）

> Internal levels of library output that are initialised to not print anything but can be overridden by programmer.

```
var ErrInvalidQos = errors.New("Invalid QoS")
```

`ErrInvalidQos` 会在数据包以非法 `Qos` 值发送时抛出错误。

> ErrInvalidQos is the error returned when an packet is to be sent with an invalid Qos value.

```
var ErrInvalidTopicEmptyString = errors.New("Invalid Topic; empty string")
```

`ErrInvalidTopicEmptyString` 会在传入的 `topic` 为空字符串时抛出错误。

> ErrInvalidTopicEmptyString is the error returned when a topic string is passed in that is 0 length.

```
var ErrInvalidTopicMultilevel = errors.New("Invalid Topic; multi-level wildcard must be last level")
```

`ErrInvalidTopicMultilevel` 会在 `topic` 值在非末尾位置存在多级通配符的情况下抛出错误。

> ErrInvalidTopicMultilevel is the error returned when a topic string is passed in that has the multi level wildcard in any position but the last.

```
var ErrNotConnected = errors.New("Not Connected")
```

`ErrNotConnected` 会在客户端没有连接代理且发生函数调用时抛出错误。

> ErrNotConnected is the error returned from function calls that are made when the client is not connected to a broker.



