# 获取币种列表
URL: `/api/common/get-coins`  
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
            "coinSymbol": "USDT",
            "icon": "https://static-coinmeta.runfast123.com/imgs/coins/D05B8596E7E0410D9B54A5FF337E30BA.png",
            "merchantId": "FENGLOU",
            "coinAddress": "TY7NUK2JY1Y3dS5kmewPi1JouYUmT1mimg",
            "updateTime": "2022-06-03 06:22:36",
            "coinFullName": "Tether USD",
            "coinName": "USDT.TRC20",
            "coinStatus": 1,
            "id": 15,
            "status": 1
        }
    ]
}
```