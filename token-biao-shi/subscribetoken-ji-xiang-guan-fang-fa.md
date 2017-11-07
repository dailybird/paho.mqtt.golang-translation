# SubscribeToken 及相关方法

## type SubscribeToken

```
type SubscribeToken struct {
    // contains filtered or unexported fields
}
```

> SubscribeToken is an extension of Token containing the extra fields required to provide information about calls to Subscribe\(\)

### func \(\*SubscribeToken\) Error

```
func (b *SubscribeToken) Error() error
```

### func \(\*SubscribeToken\) Result

```
func (s *SubscribeToken) Result() map[string]byte
```

> Result returns a map of topics that were subscribed to along with the matching return code from the broker. This is either the Qos value of the subscription or an error code.

### func \(\*SubscribeToken\) Wait

```
func (b *SubscribeToken) Wait() bool
```

> Wait will wait indefinitely for the Token to complete, ie the Publish to be sent and confirmed receipt from the broker

### func \(\*SubscribeToken\) WaitTimeout

```
func (b *SubscribeToken) WaitTimeout(d time.Duration) bool
```

> WaitTimeout takes a time in ms to wait for the flow associated with the Token to complete, returns true if it returned before the timeout or returns false if the timeout occurred. In the case of a timeout the Token does not have an error set in case the caller wishes to wait again

译注：以上译文可参考 [ConnectToken 及相关方法](/token-biao-shi/connecttoken-ji-xiang-guan-fang-fa.md)。

