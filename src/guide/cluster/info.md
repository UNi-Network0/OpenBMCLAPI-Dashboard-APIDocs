![image](https://github.com/UNi-Network0/OpenBMCLAPI-Dashboard-APIDocs/assets/68094002/b1e16c6d-5da8-4979-bc1b-f2ba7fa3d582)---
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
    "data": "python-openbmclapi"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型    | 必选 | 约束 | 中文名 | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » code    | integer | true | none |        | 状态码 |
| » message | string  | true | none |        | 信息   |
| » data    | string  | true | none |        | data   |




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
        "isenabled": true,
        "issync": false,
        "istrust": true
        "uptime": timestamp
    }
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构

状态码 **200**
| 名称          | 类型    | 必选 | 约束 | 中文名           | 说明 |
| ------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code        | integer | true | none | 状态码           | none |
| » msg     | string  | true | none | 信息                 | none |
| » data        | object  | true | none | 数据             | none |
| »» isenabled        | boolean | true | none | 是否启用      | none |
| »» issync   | boolean  | true | none | 是否同步            | none |
| »» istrust        | boolean | true | none | 是否为信任节点        | none |
| »» uptime   | boolean  | true | none | 启用时间             | none |



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
        "_id": "cluster_id",
        "fullsize": true,
        "trust": 1000 #已弃用，详见/api/cluster/status
        "noFastEnable": false
    }
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构

状态码 **200**
| 名称          | 类型    | 必选 | 约束 | 中文名           | 说明 |
| ------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code        | integer | true | none | 状态码           | none |
| » msg     | string  | true | none | 信息                 | none |
| » data        | object  | true | none | 数据             | none |
| »» name        |str | true | none | 节点名         | none |
| »» _id   | str  | true | none | 节点id            | none |
| »» fullsize   | boolean  | true | none | 是否全量             | none |
| »» trust   | str  | true | none | 信任度             | none |
| »» noFastEnable   | boolean  | true | none | 是否开启NoFastEnable             | none |

## Get 节点流量获取

GET /api/cluster/requests

获取当前启用节点统计流量

> 返回示例

> 成功

```json
[
    {
        "code": "200",
        "msg": "success"
    },
    {
        "data": {
            "hours": [
                {
                    "timestamp": 1714794779
                    "hits": 12,
                    "bytes": 13072703
                }
            ],
            "days": [
                {
                    "timestamp": 1714794779
                    "hits": 0,
                    "bytes": 0
                }
            ],
            "months": [
                {
                    "timestamp": 1714794779
                    "hits": 0,
                    "bytes": 0
                }
            ]
        }
    }
]
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构.

状态码 **200**
| 名称          | 类型    | 必选 | 约束 | 中文名           | 说明 |
| ------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code        | integer | true | none | 状态码           | none |
| » msg     | string  | true | none | 信息                 | none |
| » data        | object  | true | none | 数据             | none |
| »» hours        | List| true | none | 小时流量         | none |
| »» days   |  List | true | none | 日流量            | none |
| »» months   |List | true | none | 月流量             | none |

## Get 节点请求UA获取

GET /api/cluster/commonua

获取当前启用节点统计流量

> 返回示例

> 成功

```json
    {
        "code": "200",
        "msg": "success"
    },
    {
        "data": {
            "commonua": [
                "PCL2/1.0.0" : 114514,
                "HMCL/Java1.8.0": 114514,
                "openbmclapi-cluster/1.9.8": 100
            ]
        }
    }
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

### 返回数据结构.

状态码 **200**
| 名称          | 类型    | 必选 | 约束 | 中文名           | 说明 |
| ------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code        | integer | true | none | 状态码           | none |
| » msg     | string  | true | none | 信息                 | none |
| » data        | object  | true | none | 数据             | none |
| »» hours        | List| true | none | 小时流量         | none |
| »» days   |  List | true | none | 日流量            | none |
| »» months   |List | true | none | 月流量             | none |    



