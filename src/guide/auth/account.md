---
title: 账号相关
icon: circle-info
---

## 登录<Badge text="GET" type="info" vertical="top" />
- 接口地址: `/api/auth/login`
- 请求参数

| 名称 | 类型 | 必选                                             | 中文名 |
| ------ | ---- | ------------------------------------------------------- | ---- |
| username | string | true | 用户名 |
| password | string | true | 密码 |

- 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回参数

状态码 **200**

| 名称          | 类型    | 必选 | 约束 | 中文名           | 说明 |
| ------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code        | integer | true | none | 状态码           | none |
| » msg     | string  | true | none | 信息                 | none |
| » data        | object  | true | none | 数据             | none |
| »» id         | integer | true | none | id               | none |
| »» username   | string  | true | none | 用户名           | none |
| »» role       | integer | true | none | 角色             | none |
| »» disabled   | boolean | true | none | 是否禁用         | none |
| »» permission | integer | true | none | 权限             | none |
| »» otp        | boolean | true | none | 是否开启二步验证 | none |

- 返回示例
```json
{
  "code": 200,
  "msg": "success",
  "data": {
    "id": 1,
    "username": "admin",
    "disabled": false,
    "role": "admin"
    "permission": 0,
    "otp": true
  }
}
```

## 注销<Badge text="GET" type="info" vertical="top" />
- 接口地址: `/api/auth/logout`
- 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | 成功 | Inline   |

- 返回参数

状态码 **200**
| 名称          | 类型    | 必选 | 约束 | 中文名           | 说明 |
| ------------- | ------- | ---- | ---- | ---------------- | ---- |
| » code        | integer | true | none | 状态码           | none |
| » msg     | string  | true | none | 信息                 | none |

- 返回示例
```json
{
  "code": 200,
  "msg": "success",
}
```