# 查询用户资产（自动注册）
URL: `/api/common/query-assets`  
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
    "data": [
        {
            "id": 265,
            "balance": 0,
            "icon": "https://xx.xxxxx.com/imgs/coins/C701FCCFB1ED4161B1E8E826B27E7D49.png",
            "address": "0x5F44bF704887b62ef4DcB24f3d1cfDb6E42cA19b",
            "memberId": 1122,
            "coinName": "USDC.ERC20",
            "coinFullName": "USD Coin",
            "coinSymbol": "USDC",
            "coinStatus": 0
        },
        {
            "id": 266,
            "balance": 0,
            "icon": "https://xx.xxxxx.com/imgs/coins/D05B8596E7E0410D9B54A5FF337E30BA.png",
            "address": "TY7NUK2JY1Y3dS5kmewPi1JouYUmT1mimg",
            "memberId": 1122,
            "coinName": "USDT.TRC20",
            "coinFullName": "Tether USD",
            "coinSymbol": "USDT",
            "coinStatus": 1
        }
    ]
}
```