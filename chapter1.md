# 变量

```go
var (
    ERROR    *log.Logger
    CRITICAL *log.Logger
    WARN     *log.Logger
    DEBUG    *log.Logger
)
```

作为内置的输出库，默认情况下，在不对其进行配置时，\`paho.mqtt.golang\` 是不会进行输出打印的。但开发者可以自行配置他们。（比如：\`mqtt.DEBUG = log.New\(os.Stdout, "", 0\)\` 可以使得）



