# UnsubscribeToken 及相关方法

## type UnsubscribeToken

```
type UnsubscribeToken struct {
    // contains filtered or unexported fields
}
```

> UnsubscribeToken is an extension of Token containing the extra fields required to provide information about calls to Unsubscribe\(\).

### func \(\*UnsubscribeToken\) Error

```
func (b *UnsubscribeToken) Error() error
```

### func \(\*UnsubscribeToken\) Wait

```
func (b *UnsubscribeToken) Wait() bool
```

> Wait will wait indefinitely for the Token to complete, ie the Publish to be sent and confirmed receipt from the broker

### func \(\*UnsubscribeToken\) WaitTimeout

```
func (b *UnsubscribeToken) WaitTimeout(d time.Duration) bool
```

> WaitTimeout takes a time in ms to wait for the flow associated with the Token to complete, returns true if it returned before the timeout or returns false if the timeout occurred. In the case of a timeout the Token does not have an error set in case the caller wishes to wait again

译注：以上译文可参考 [ConnectToken 及相关方法](/token-biao-shi/connecttoken-ji-xiang-guan-fang-fa.md)。

