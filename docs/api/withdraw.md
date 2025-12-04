# 提现
URL: `/api/common/withdraw`  
Method: `POST`

> 参数   

| 参数名            | 类型         | 是否必须   | 描述                                |
| ------------     | ----------- | --------- | ---------------------------------- |
| refOrderId       | string      | YES       | 商家订单ID（商户内部）                 |
| refUserId        | string      | YES       | 用户ID（商户内部）                    |
| amount           | number      | YES       | 数量                                |
| coinName         | string      | YES      | 数字币币种 (USDT.ERC20/USDT.TRC20)    |
| toAddress        | string      | YES      | 提现目标地址                          |

> Request

```json
{
    "refOrderId": "B93FCBC849D442DA901548AE6F0EA890",
    "refUserId": "13800138000",
    "amount": 50,
    "coinName": "USDT.TRC20",
    "toAddress": "TKf3Rqc7f3fd2U7CP4xVbrDmaqYzsKPYR5"
}
```

> Response   

```json
{
    "code": 200,
    "message": "Success"
}
```