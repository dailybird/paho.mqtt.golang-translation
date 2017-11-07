# PublishToken 及相关方法

## type PublishToken

```
type PublishToken struct {
    // contains filtered or unexported fields
}
```

> PublishToken is an extension of Token containing the extra fields required to provide information about calls to Publish\(\)

### func \(\*PublishToken\) Error

```
func (b *PublishToken) Error() error
```

### func \(\*PublishToken\) MessageID

```
func (p *PublishToken) MessageID() uint16
```

> MessageID returns the MQTT message ID that was assigned to the Publish packet when it was sent to the broker

### func \(\*PublishToken\) Wait

```
func (b *PublishToken) Wait() bool
```

> Wait will wait indefinitely for the Token to complete, ie the Publish to be sent and confirmed receipt from the broker.

### func \(\*PublishToken\) WaitTimeout

```
func (b *PublishToken) WaitTimeout(d time.Duration) bool
```

> WaitTimeout takes a time in ms to wait for the flow associated with the Token to complete, returns true if it returned before the timeout or returns false if the timeout occurred. In the case of a timeout the Token does not have an error set in case the caller wishes to wait again.

译注：以上译文可参考 [ConnectToken 及相关方法](/token-biao-shi/connecttoken-ji-xiang-guan-fang-fa.md)。

