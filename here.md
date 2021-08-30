# Nsq源码解析

version: 1.2.1-alpha
### nsqlookupd
http_api
- 获取所有的topic
http://localhost:4161/topics
- 获取指定topic下的信息
http://localhost:4161/topic?=my_topic_test
```
{
    "channels": [
        "my_channel_a"
    ],
    "producers": [
        {
            "remote_address": "127.0.0.1:58157",
            "hostname": "localhost",
            "broadcast_address": "localhost",
            "tcp_port": 4150,
            "http_port": 4151,
            "version": "1.2.1-alpha"
        }
    ]
}
```
- 获取指定topic下的所有channels
http://localhost:4161/channels?topic=my_topic_test
```
{
    "channels": [
        "my_channel_a"
    ]
}
```
- 创建topic
http://localhost:4161/topic/create?topic=create_topic_test

## 疑问
- nsqlookupd启动后创建的的topic基于map来存储,万一机器挂了,数据岂不是全都没了？
