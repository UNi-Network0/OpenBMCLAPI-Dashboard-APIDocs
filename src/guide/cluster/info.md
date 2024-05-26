---
title: 节点相关
icon: circle-info
---


## 节点类型获取<Badge text="GET" type="info" vertical="top" />
> 获取当前启用节点客户端类型
- 接口地址: `/api/cluster/type`
- 例：无
- 请求参数：无
- 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |
- 返回数据结构

状态码 **200**
| 名称      | 类型     | 必选 | 约束 | 中文名  | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » type    | string  | true | none |        | 节点版本   |
| » version    | integer  | true | none |        | 节点客户端版本号   |
- 返回示例
```json
{
    "type": "python-openbmclapi",
    "version": "11.45.14"
}
```


## 节点状态获取<Badge text="GET" type="info" vertical="top" />
> 获取当前启用节点客户端类型
- 接口地址: `/api/cluster/status`
- 例：无
- 请求参数：无
- 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构

状态码 **200**
| 名称                 | 类型    | 必选 | 约束 | 中文名             | 说明                        |
| ------------------- | ------- | ---- | ---- | ------------------ | ---------------            |none                       |
| » isEnabled      | boolean | true | none | 是否启用           | none                       |
| » isSynchronized | boolean | true | none | 是否已经同步       | 如果正在同步文件，则为 false |
| » isTrusted      | boolean | true | none | 是否为受信任的节点  | none                       |
| » uptime         | integer | true | none | 启用时间           | 是一个 timestamp         
- 返回示例
```json
{
    "isEnabled": true,
    "isSynchronized": false,
    "isTrusted": true,
    "uptime": 0
}
```

## 节点信息获取<Badge text="GET" type="info" vertical="top" />
> 获取当前启用节点客户端类型
- 接口地址: `/api/cluster/info`
- 例：无
- 请求参数：无
- 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构

状态码 **200**
| 名称              | 类型    | 必选  | 约束 | 中文名                 | 说明                       |
| ----------------- | ------- | ---- | ---- | --------------------- | -------------------------- |  
| » name         | string  | true | none | 节点名                 | none                       |
| » clusterId    | string  | true | none | 节点 id                | 是一个 32 位长的 hex 字符串 |         
| » isFullsize   | boolean | true | none | 是否是全量节点         | none                       |
| » trust        | integer | true | none | 信任度                 | **[已经弃用]**             |
| » noFastEnable | boolean | true | none | 是否开启NoFastEnable   | none                      | 
- 返回示例
```json
{
    "name": "name",
    "clusterId": "clusterId",
    "fullsize": true,
    "trust": 1000, //已弃用，详见/api/cluster/status
    "noFastEnable": false
}
```


## 节点流量获取<Badge text="GET" type="info" vertical="top" />
> 获取当前启用节点统计流量
- 接口地址: `/api/cluster/requests`
- 例：无
- 请求参数：无
- 返回结果: 

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构.

状态码 **200**
| 名称                  | 类型     | 必选 | 约束 | 中文名           | 说明 |
| --------------------- | ------- | ---- | ---- | ---------------- | ---- |
| » data                | object  | true | none | 数据             | none |
| » hours            | List    | true | none | 小时流量         | none |
| » timestamp      | integer | true | none | 时间戳           | none |
| » hits           | integer | true | none | 访问量           | none |
| » bytes          | integer | true | none | 流量             | none |
| » days             | List    | true | none | 日流量           | none |
| » months           | List    | true | none | 月流量           | none |

- 返回示例
```json
{
    "data": {
        "hours": [
            {
                "timestamp": 1714794779,
                "hits": 12,
                "bytes": 13072703
            }
        ],
        "days": [
            {
                "timestamp": 1714794779,
                "hits": 0,
                "bytes": 0
            }
        ],
        "months": [
            {
                "timestamp": 1714794779,
                "hits": 0,
                "bytes": 0
            }
        ]
    }
}
```


## 节点请求 UA 获取<Badge text="GET" type="info" vertical="top" />
> 获取当前启用节点统计流量
- 接口地址: `/api/cluster/commonua`
- 例：无
- 请求参数：无
- 返回结果: 

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构.

状态码 **200**
| 名称          | 类型     | 必选  | 约束 | 中文名           | 说明                        |
| ------------- | -------- | ---- | ---- | ---------------- | ----                       |
| » data        | object   | true | none | 数据             | none                       |
| » commonUA | object   | true | none | 常见 UA          | 根据请求量排序的 UA 统计数据 |

- 返回示例
```json
{
    "data": {
        "commonUA": {
            "PCL2" : 114514,
            "HMCL": 114514,
            "openbmclapi-cluster": 100
        }
    }
}
```