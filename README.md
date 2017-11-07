# 前言

此翻译并非完全按照官方文档（[ https://godoc.org/github.com/eclipse/paho.mqtt.golang](https://godoc.org/github.com/eclipse/paho.mqtt.golang) ）的顺序进行。文档并非逐字逐句翻译，其中会有一些自己的理解。

译文下方会以引用的方式附带原文，如有翻译不当的地方，请随时指正，谢谢。

注：查询了一些资料，在 MQTT 协议中，服务器和客户端的定义取决于连接代理（ Broker ）的对象是对某一 Topic 的订阅（ Subscribe ）还是发布 （  Publish ）。就个人理解而言，在文档中，Server 服务器指的是对某一 Topic 的订阅者，而 Client 客户端指的是连接代理（ Broker ）的对象。**请大家注意文档译文和字面意思的区别**。

