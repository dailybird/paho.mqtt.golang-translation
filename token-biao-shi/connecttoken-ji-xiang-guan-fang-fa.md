# ConnectToken 及相关方法

### type ConnectToken

```
type ConnectToken struct {
    // contains filtered or unexported fields
}
```

`ConnectToken` 是`Token` 的一个扩展，包含了一些用于在 `Connect` 方法调用之后需要提供的额外字段。

> ConnectToken is an extension of Token containing the extra fields required to provide information about calls to Connect\(\).

### func \(\*ConnectToken\) Error

```
func (b *ConnectToken) Error() error
```

### func \(\*ConnectToken\) ReturnCode

```
func (c *ConnectToken) ReturnCode() byte
```

`ReturnCode` 返回由 `Connect` 方法响应的一个确认码。

> ReturnCode returns the acknowlegement code in the connect sent in response to a Connect\(\).

### func \(\*ConnectToken\) Wait

```
func (b *ConnectToken) Wait() bool
```

`Wait` 将会在 `Token` 完成前无线等待。比如发送的发布（ `Publish` ）消息与获取代理的接收确认。

> Wait will wait indefinitely for the Token to complete, ie the Publish to be sent and confirmed receipt from the broker.

### func \(\*ConnectToken\) WaitTimeout

```
func (b *ConnectToken) WaitTimeout(d time.Duration) bool
```

`WaitTimeout` 会花费若干若干毫秒的时间等待与 `Token` 完成有关的流程。如果在超时之前收到返回，则会返回 `true`，当发生超时时会返回 `false`。当发生超时情况时，如果调用方需要再次等待，则不会进入抛出错误。

> WaitTimeout takes a time in ms to wait for the flow associated with the Token to complete, returns true if it returned before the timeout or returns false if the timeout occurred. In the case of a timeout the Token does not have an error set in case the caller wishes to wait again.



