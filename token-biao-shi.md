# Token 标识

### type Token

```
type Token interface {
    Wait() bool
    WaitTimeout(time.Duration) bool
    Error() error
}
```

`Token` 是一个接口，用于表示一次动作是否执行完成。

> Token defines the interface for the tokens used to indicate when actions have completed.

译注：`Token` 在 `paho.mqtt.golang` 中很是重要，比如我们需要在对连接进行其他操作前，通过` Connect()` 方法返回的 `token` 来判断连接是否已经成功建立。

