# DisconnectToken 及相关方法

## type DisconnectToken

```
type DisconnectToken struct {
    // contains filtered or unexported fields
}
```

`DisconnectToken` 是`Token` 的一个扩展，包含了一些用于在 `Disconnect` 方法调用之后需要提供的额外字段。

> DisconnectToken is an extension of Token containing the extra fields required to provide information about calls to Disconnect\(\)

### func \(\*DisconnectToken\) Error

```
func (b *DisconnectToken) Error() error
```

### func \(\*DisconnectToken\) Wait

```
func (b *DisconnectToken) Wait() bool
```

> Wait will wait indefinitely for the Token to complete, ie the Publish to be sent and confirmed receipt from the broker

### func \(\*DisconnectToken\) WaitTimeout

```
func (b *DisconnectToken) WaitTimeout(d time.Duration) bool
```

> WaitTimeout takes a time in ms to wait for the flow associated with the Token to complete, returns true if it returned before the timeout or returns false if the timeout occurred. In the case of a timeout the Token does not have an error set in case the caller wishes to wait again

译注：以上译文可参考 [ConnectToken 及相关方法](/token-biao-shi/connecttoken-ji-xiang-guan-fang-fa.md)。

