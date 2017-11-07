# FileStore 及相关方法

### type FileStore

```
type FileStore struct {
    sync.RWMutex
    // contains filtered or unexported fields
}
```

`FileStore` 实现了 `Store` 接口，其使用文件系统提供消息的持久化，甚至是在客户端出错的情况下。这是为每个正在运行的客户端使用单独的目录而设计的。如果你在同一个文件系统中运行了多个客户端，那么需要分别为每一个客户端指定不同的存储路径。

> FileStore implements the store interface using the filesystem to provide true persistence, even across client failure. This is designed to use a single directory per running client. If you are running multiple clients on the same filesystem, you will need to be careful to specify unique store directories for each.

### func NewFileStore

```
func NewFileStore(directory string) *FileStore
```

`NewFileStore` 将会创建一个 `FileStore` 对象，用以在指定的目录存储自己消息。

> NewFileStore will create a new FileStore which stores its messages in the directory provided.

### func \(\*FileStore\) All

```
func (store *FileStore) All() []string
```

`All` 将会列出所有当前存储于该 `FileStore` 中与消息相关联的 `Key` 值。

> All will provide a list of all of the keys associated with messages currently residing in the FileStore.

### func \(\*FileStore\) Close

```
func (store *FileStore) Close()
```

`Close` 将会禁用正在使用中的 `FileStore`。

> Close will disallow the FileStore from being used.

### func \(\*FileStore\) Del

```
func (store *FileStore) Del(key string)
```

`Del` 接收一个 `Key` 值（译注：源于 `All` 方法的返回），并将其对应的消息从 `FileStore` 中删除。

> Del will remove the persisted message associated with the provided key from the FileStore.

### func \(\*FileStore\) Get

```
func (store *FileStore) Get(key string) packets.ControlPacket
```

`Get` 接收一个 `Key` 值，并返回其对应的消息。

> Get will retrieve a message from the store, the one associated with the provided key value.

### func \(\*FileStore\) Open

```
func (store *FileStore) Open()
```

`Open` 将会启用 `FileStore`。

> Open will allow the FileStore to be used.

### func \(\*FileStore\) Put

```
func (store *FileStore) Put(key string, m packets.ControlPacket)
```

`Put` 会将一个消息及其对应的 `key` 值加入到 `FileStore` 中。

> Put will put a message into the store, associated with the provided key value.

### func \(\*FileStore\) Reset

```
func (store *FileStore) Reset()
```

`Reset` 将会移除所有存储于 `FileStore` 中的消息。

> Reset will remove all persisted messages from the FileStore.



