# 充值/支付/提现回调（商户实现订阅）
URL: `${merchant_api_url}/callback`  
Method: `POST`

> 参数   
 
请求头参数： s0 (商户验签)

##### deposit-充值

| 参数名            | 类型         | 是否必须    | 描述                                |
| ------------     | ----------- | ---------  | ---------------------------------- |
| method           | string      | YES        | withdraw                           |
| merchantId      | string      | YES       | 商户ID                              |
| refUserId      | string      | YES        | 用户ID（商户内部）                    |
| refOrderId     | string      | NO         | 订单ID（商户内部）                   |
| orderId         | string      | YES        | 订单ID （Metarsier 订单）         |
| toUser          | string      | YES        | 用户ID （Metarsier 用户）         |
| toAddress       | string      | YES        | 目标地址                            |
| amount           | string      | YES        | 数量                                |
| fee              | string      | NO        | 手续费                              |
| coinName        | string      | YES        | 数字币币种 (USDT.ERC20/USDT.TRC20)   |
| status           | string      | YES        | 状态 1: INITIAL, 2: PROCESSING, 3: FINISHED, 4: FAILED, 5: CANCELED |

> Request (deposit-充值)

```json
{
    "method": "deposit",
    "merchantId": "XXXXXX",
    "refUserId": "XXXXXXXXX",
    "refOrderId": "",
    "orderId": "B93FCBC849D442DA901548AE6F0EA890",
    "toUser": "BF7458745",
    "toAddress": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5",
    "amount": "50",
    "fee": "",
    "coinName": "USDT.TRC20",
    "status": "3"
}
```

##### payment-支付: create-order

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| method           | string      | YES       | payment                            |
| merchantId      | string      | YES       | 商户ID                              |
| refUserId      | string      | YES       | 用户ID（商户内部）                    |
| refOrderId     | string      | YES       | 订单ID（商户内部）                   |
| orderId         | string      | YES       | 订单ID （Metarsier 订单）         |
| toUser          | string      | YES       | 用户ID （Metarsier 用户）         |
| toAddress       | string      | YES       | 目标地址                            |
| amount           | string      | YES       | 数量                               |
| fee              | string      | NO        | 手续费                              |
| coinName        | string      | YES       | 数字币币种 (USDT.ERC20/USDT.TRC20)  |
| status           | string      | YES       | 状态 1: INITIAL, 2: PROCESSING, 3: FINISHED, 4: FAILED, 5: CANCELED |

> Request (payment-支付: create-order)

```json
{
    "method": "payment",
    "merchantId": "XXXXXX",
    "refUserId": "XXXXXXXXX",
    "refOrderId": "20220725103012560001",
    "orderId": "B93FCBC849D442DA901548AE6F0EA890",
    "toUser": "BF7458745",
    "toAddress": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5",
    "amount": "50",
    "fee": "",
    "coinName": "USDT.TRC20",
    "status": "3"
}
```

##### withdraw-提现

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| method           | string      | YES       | withdraw                           |
| merchantId      | string      | YES       | 商户ID                              |
| refUserId      | string      | YES       | 用户ID（商户内部）                    |
| refOrderId     | string      | YES       | 订单ID（商户内部）                   |
| orderId         | string      | YES       | 订单ID （Metarsier 订单）         |
| toAddress       | string      | YES       | 目标地址                            |
| amount           | string      | YES       | 数量                               |
| fee              | string      | YES       | 手续费                              |
| coinName        | string      | YES       | 数字币币种 (USDT.ERC20/USDT.TRC20)  |
| status           | string      | YES       | 状态 1: INITIAL, 2: PROCESSING, 3: FINISHED, 4: FAILED, 5: CANCELED |
| riskStatus       | string      | YES        | 状态 0: 无, 1: 风险地址|

> Request (withdraw-提现)

```json
{
    "method": "withdraw",
    "merchantId": "XXXXXX",
    "refUserId": "XXXXXXXXX",
    "refOrderId": "20220725103012560001",
    "orderId": "B93FCBC849D442DA901548AE6F0EA890",
    "toAddress": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5",
    "amount": "50",
    "fee": "1",
    "coinName": "USDT.TRC20",
    "status": "3",
    "riskStatus": "0"
}
```

> Response   

##### 响应code为200，并且message为"Success"代表成功，并回传商户自己的订单ID

```json
{
    "code": 200,
    "message": "Success",
    "data": {
        "refOrderId": "20220725103012560001"
    }
}
```