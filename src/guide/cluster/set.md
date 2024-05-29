# 必须验证账户之后才能使用该 API，否则操作有关设置的返回 403，获取信息的返回 401

---
title: 节点设置
icon: circle-info
---

## 添加节点储存<Badge text="GET" type="info" vertical="top" />
> 添加节点储存
- 接口地址: `/api/cluster/set/storage/add`
- 例：`/api/cluster/set/storage/delete?type="webdav"&username="test&password="test&endpoint="http://127.0.0.1/dav`
- 请求参数

| 名称       | 位置  | 类型   | 必选 | 中文名           | 说明                |
| ---------- | ---- | ------ | ---- | --------------- | ------------------- |
| type       | body | string | 是   | 储存类型         | 可选 webdav / local |
| username   | body | string | 是   | WebDav用户名     | WebDav用户名        |
| password   | body | string | 是   | WebDav密码       | WebDav密码          |
| endpoint   | body | string | 是   | WebDav Endpoint | WebDav文件储存地址   |
| localpath  | body | string | 是   | 本地储存地址     | 本地储存地址         |

- 返回结果: 

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构

状态码 **200**
| 名称      | 类型     | 必选 | 约束 | 中文名 | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » data    | string  | true | none |        | data   |

- 返回示例
```json
{
    "data": "WebDav-Storage" 
}
```

## 删除节点储存<Badge text="GET" type="info" vertical="top" />
> 删除节点储存
- 接口地址: `/api/cluster/set/storage/delete`
- 例：`/api/cluster/set/storage/delete?type="webdav"`
- 请求参数

| 名称       | 位置  | 类型   | 必选 | 中文名      | 说明                |
| ---------- | ---- | ------ | ---- | ---------- | ------------------- |
| type       | body | string | 是   | 储存类型    | 可选 webdav / local |

- 返回结果: 

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构

状态码 **200**
| 名称      | 类型     | 必选 | 约束 | 中文名 | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » data    | string  | true | none |        | data   |

- 返回示例
```json
{
    "data": "WebDav-Storage" 
}
```

## 设置节点域名（仅byoc=true时）<Badge text="GET" type="info" vertical="top" />
> 设置节点域名
- 接口地址: `/api/cluster/set/domain`
- 例：`/api/cluster/set/domain?dm="666.com"`
- 请求参数

| 名称       | 位置 | 类型    | 必选 | 中文名     | 说明        |
| ---------- | ---- | ------ | ---- | ---------- | ---------- |
| dm         | body | string | 是   | 域名       | 无          |
- 返回结果: 

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构

状态码 **200**

| 名称      | 类型    | 必选  | 约束 | 中文名 | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » code    | integer | true | none |        | 状态码 |

- 返回示例
```json
{
    "code": 200
}
```

## 设置byoc（是否使用自己的域名）<Badge text="GET" type="info" vertical="top" />
> 设置节点域名
- 接口地址: `/api/cluster/set/byoc`
- 例：`/api/cluster/set/byoc?byoc=true`
- 请求参数

| 名称       | 位置 | 类型     | 必选 | 中文名     | 说明       |
| ---------- | ---- | ------- | ---- | ---------- | ---------- |
| byoc       | body | boolean | 是   | 域名       | 无         |
- 返回结果: 

| 状态码 | 状态码含义                                               | 说明 | 数据模型  |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回数据结构

状态码 **200**

| 名称      | 类型     | 必选 | 约束 | 中文名 | 说明   |
| --------- | ------- | ---- | ---- | ------ | ------ |
| » code    | integer | true | none |        | 状态码 |

- 返回示例
```json
{
    "code": 200
}
```
