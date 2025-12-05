# 查询充值地址（自动注册）
URL: `/api/common/get-payment-url`  
Method: `POST`

> 参数   

| 参数名        | 类型         | 是否必须   | 描述                                |
| ------------ | ----------- | --------- | ---------------------------------- |
| refUserId  | string      | YES       | 用户ID（商户内部）                    |

> Request   

```json
{
    "refUserId": "13800138000"
}
```

> Response   

```json
{
    "code": 200,
    "message": "Success",
    "data": "https://metapay-web.powerbtent.com/GW511292/92079"
}
```