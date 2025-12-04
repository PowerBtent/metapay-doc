# 创建支付订单
URL: `/api/common/create-order`  
Method: `POST`

> 参数   

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| refUserId      | string      | YES       | 用户ID（商户内部）                    |
| refOrderId     | string      | YES       | 订单ID（商户内部）                    |
| amount           | number      | NO        | 数量                                |
| coinName        | string      | NO        | 数字币币种 (USDT.ERC20/USDT.TRC20)   |
| priceAmount     | number      | NO        | 法币金额                            |
| priceCurrency   | string      | NO        | 法币币种 (CNY/USD/PHP/JPY)          |
| receiveCurrency | string      | NO        | 提款币种 (USDT.ERC20/USDT.TRC20)    |
| returnUrl       | string      | NO        | 跳转返回商家地址                        |

> Request (数字币充值) 

```json
{
    "refUserId": "13800138000",
    "refOrderId": "20220725103012560001",
    "amount": 50,
    "coinName": "USDT.TRC20",
    "returnUrl": "https://xxxxx.com"
}
```

> Request (法币计价充值) 

```json
{
    "refUserId": "13800138000",
    "refOrderId": "20220725103012560001",
    "priceAmount": 50,
    "priceCurrency": "CNY",
    "returnUrl": "https://xxxxx.com"
}
```

> Response   

```json
# 使用payment_url跳转支付
{
    "code": 200,
    "message": "Success",
    "data": {
        "amount": 22,
        "coinName": "USDT.TRC20",
        "createTime": "2022-07-26 16:33:23",
        "isRefundable": 0,
        "orderId": "B93FCBC849D442DA901548AE6F0EA890",
        "overpaidAmount": 0,
        "paymentUrl": "https://pay.digitbeetle.com/invoice/B93FCBC849D442DA901548AE6F0EA890",
        "priceAmount": 0,
        "priceCurrency": null,
        "receiveAmount": 0,
        "receiveCurrency": "",
        "underpaidAmount": 0
    }
}
```