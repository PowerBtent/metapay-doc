# 取消订单
URL: `/api/common/cancel-order`  
Method: `POST`

> 参数   

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| refUserId        | string      | YES       | 用户ID（商户内部）                    |
| refOrderId       | string      | NO        | 订单ID（商户内部，不传就是所有的订单）   |
| type             | number      | YES       | 订单类型 （1:充值, 2:支付, 3:提现）            |

> Request

```json
{
    "refUserId": "13800138000",
    "refOrderId": "20220725103012560001",
    "type": 2,
}
```

> Response   

```json
{
    "code": 200,
    "message": "Success"
}
```