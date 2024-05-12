---
title: 节点相关
icon: circle-info
---


## Get 节点类型获取

GET /api/cluster/type

获取当前启用节点客户端类型

> 返回示例

> 成功

```json
{
    "code": 200,
    "msg": "success",
    "type": "python-openbmclapi",
    "version": "11.45.14"
}
```

### 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型     | 必选 | 约束 | 中文名  | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » code    | integer | true | none |        | 状态码 |
| » message | string  | true | none |        | 信息   |
| » type    | string  | true | none |        | 节点客户端版本   |




## Get 节点状态获取

GET /api/cluster/status

获取当前启用节点客户端类型

> 返回示例

> 成功

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "isEnabled": true,
        "isSynchronized": false,
        "isTrusted": true,
        "uptime": 0
    }
}
```

### 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构

状态码 **200**
| 名称                 | 类型    | 必选 | 约束 | 中文名             | 说明                        |
| ------------------- | ------- | ---- | ---- | ------------------ | ---------------            |
| » code              | integer | true | none | 状态码             | none                       |
| » msg               | string  | true | none | 信息               | none                       |
| » data              | object  | true | none | 数据               | none                       |
| \|-» isEnabled      | boolean | true | none | 是否启用           | none                       |
| \|-» isSynchronized | boolean | true | none | 是否已经同步       | 如果正在同步文件，则为 false |
| \|-» isTrusted      | boolean | true | none | 是否为受信任的节点  | none                       |
| \|-» uptime         | integer | true | none | 启用时间           | 是一个 timestamp            |



## Get 节点信息获取

GET /api/cluster/info

获取当前启用节点客户端类型

> 返回示例

> 成功

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "name": "name",
        "clusterId": "clusterId",
        "fullsize": true,
        "trust": 1000, //已弃用，详见/api/cluster/status
        "noFastEnable": false
    }
}
```

### 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构

状态码 **200**
| 名称              | 类型    | 必选  | 约束 | 中文名                 | 说明                       |
| ----------------- | ------- | ---- | ---- | --------------------- | -------------------------- |  
| » code            | integer | true | none | 状态码                 | none                       |
| » msg             | string  | true | none | 信息                   | none                       |
| » data            | object  | true | none | 数据                   | none                       |
| \|-» name         | string  | true | none | 节点名                 | none                       |
| \|-» clusterId    | string  | true | none | 节点 id                | 是一个 32 位长的 hex 字符串 |         
| \|-» isFullsize   | boolean | true | none | 是否是全量节点         | none                       |
| \|-» trust        | integer | true | none | 信任度                 | **[已经弃用]**             |
| \|-» noFastEnable | boolean | true | none | 是否开启NoFastEnable   | none                       |

## Get 节点流量获取

GET /api/cluster/requests

获取当前启用节点统计流量

> 返回示例

> 成功

```json
{
    "code": 200,
    "msg": "success",
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

### 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构.

状态码 **200**
| 名称                  | 类型     | 必选 | 约束 | 中文名           | 说明 |
| --------------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code                | integer | true | none | 状态码           | none |
| » msg                 | string  | true | none | 信息             | none |
| » data                | object  | true | none | 数据             | none |
| \|-» hours            | List    | true | none | 小时流量         | none |
| --\|-» timestamp      | integer | true | none | 时间戳           | none |
| --\|-» hits           | integer | true | none | 访问量           | none |
| --\|-» bytes          | integer | true | none | 流量             | none |
| \|-» days             | List    | true | none | 日流量           | none |
| \|-» months           | List    | true | none | 月流量           | none |

## Get 节点请求 UA 获取

GET /api/cluster/commonua

获取当前启用节点统计流量

> 返回示例

> 成功

```json
{
    "code": 200,
    "msg": "success",
    "data": {
        "commonUA": {
            "PCL2" : 114514,
            "HMCL": 114514,
            "openbmclapi-cluster": 100
        }
    }
}
```

### 返回结果

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构.

状态码 **200**
| 名称          | 类型     | 必选  | 约束 | 中文名           | 说明                        |
| ------------- | -------- | ---- | ---- | ---------------- | ----                       |
| » code        | integer  | true | none | 状态码           | none                       |
| » msg         | string   | true | none | 信息             | none                       |
| » data        | object   | true | none | 数据             | none                       |
| \|-» commonUA | object   | true | none | 常见 UA          | 根据请求量排序的 UA 统计数据 |
