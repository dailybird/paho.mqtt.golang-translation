# MemoryStore 及相关方法

## type MemoryStore

```
type MemoryStore struct {
    sync.RWMutex
    // contains filtered or unexported fields
}
```

`MemoryStore` 是一个 `Store` 接口的实现，其完全基于内存提供「持久化」机制。这一持久化机制仅在客户端实例存在的情况下有效。

> MemoryStore implements the store interface to provide a "persistence" mechanism wholly stored in memory. This is only useful for as long as the client instance exists.

### func NewMemoryStore

```
func NewMemoryStore() *MemoryStore
```

`NewMemoryStore` 返回一个 `NewMemoryStore` 实例的指针。这一实例只有在 `Open` 方法调用之后才会被初始化并就绪。

> NewMemoryStore returns a pointer to a new instance of MemoryStore, the instance is not initialized and ready to use until Open\(\) has been called on it.

### func \(\*MemoryStore\) All

```
func (store *MemoryStore) All() []string
```

`All` 返回了一个字符串切片，包含所有存储于当前 `MemoryStore` 中的 `Key` 值。

> All returns a slice of strings containing all the keys currently in the MemoryStore.

### func \(\*MemoryStore\) Close

```
func (store *MemoryStore) Close()
```

`Close` 将会禁止 `MemoryStore` 中的修改操作。

> Close will disallow modifications to the state of the store.

### func \(\*MemoryStore\) Del

```
func (store *MemoryStore) Del(key string)
```

`Del` 接收一个 `Key` 值（译注：源于 `All` 方法的返回），并在 `MemoryStore` 中搜索这一 `Key` 值，如果找到则将于该 `Key` 值关联的消息指针从中删除。

> Del takes a key, searches the MemoryStore and if the key is found deletes the Message pointer associated with it.

### func \(\*MemoryStore\) Get

```
func (store *MemoryStore) Get(key string) packets.ControlPacket
```

`Get` 接收一个 `Key` 值，并在 `MemoryStore` 中进行搜索，如果有 `Key` 值匹配，则返回该消息的指针，反之则返回 `nil`。

> Get takes a key and looks in the store for a matching Message returning either the Message pointer or nil.

### func \(\*MemoryStore\) Open

```
func (store *MemoryStore) Open()
```

`Open` 将会初始化 `MemoryStore` 实例。

> Open initializes a MemoryStore instance.

### func \(\*MemoryStore\) Put

```
func (store *MemoryStore) Put(key string, message packets.ControlPacket)
```

`Put` 接收一个 `Key` 和 一个消息指针，并将该消息存储。

> Put takes a key and a pointer to a Message and stores the message.

### func \(\*MemoryStore\) Reset

```
func (store *MemoryStore) Reset()
```

`Reset` 会消除所有在该 `MemoryStore` 中持久化的消息。

> Reset eliminates all persisted message data in the store.



