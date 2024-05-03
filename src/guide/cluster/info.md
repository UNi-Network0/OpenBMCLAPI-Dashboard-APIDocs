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
        "issync": false
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
| »» isenabled        | boolean | true | none | id         | none |
| »» issync   | boolean  | true | none | 用户名             | none |


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
        "trust": "trust",
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

GET /api/cluster/data

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
                    "hits": 12,
                    "bytes": 13072703
                }
            ],
            "days": [
                {
                    "hits": 0,
                    "bytes": 0
                }
            ],
            "months": [
                {
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
| »» hours        |str | true | none | 小时流量         | none |
| »» days   | str  | true | none | 日流量            | none |
| »» months   | boolean  | true | none | 月流量             | none |


