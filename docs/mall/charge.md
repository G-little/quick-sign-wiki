# VIP相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

vip 相关接口

## 产品说明



## 关键流程说明

## 接口说明


#### 1.0 vip 充值

##### 接口说明

vip 充值首页

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /charge/index |

#####  输入参数

无


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "payTypes": [  // 支付方式
            {
                "typeName": "ALIPAYCASH",
                "comment": "支付宝支付",
                "thumbnail": null
            },
            {
                "typeName": "WX_APP",
                "comment": "微信支付",
                "thumbnail": null
            }
        ],
        "chargeList": [  //充值列表
            {
                "id": 1,
                "amount": 100.00,
                "bgUrl": null,
                "comment": null,
                "givingVip": false,
                "timeType": null,
                "timeLen": null,
                "addTime": null,
                "sortOrder": null,
                "deleted": false
            } 
         ]
    }
} 
```



#### 1.1 充值支付

##### 接口说明

vip 充值首页

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /charge/pay |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是|  int  |  状态 |  购物车ID |
| payType      | 是|  string  |  支付类型 |  |




#####  错误说明




#####  返回实例
```json  
    
    {
    "c": 0,
    "m": null,
    "d": {
        "payOrderId": null,
        "outPayOrderId": null,
        "callPayInfo": "alipay_sdk=alipay-sdk-java-dynamicVersionNo&app_id=2021001181693812&biz_content=%7B%22out_trade_no%22%3A%22PRE2007242141242862121320331011%22%2C%22product_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22subject%22%3A%22%E4%B8%AD%E6%A0%87%E4%BC%98%E9%80%89%22%2C%22timeout_express%22%3A%2230m%22%2C%22total_amount%22%3A%22100.0%22%7D&charset=UTF-8&format=json&method=alipay.trade.app.pay&notify_url=http%3A%2F%2Fxiaogang.org.cn&sign=BZ0%2FQN7aoQlxA3A0Whw8h0ON00Wb%2BLXb0hp7w317TtTnj9U%2Fsst%2F02mvUlfbeGYaydAkGUmMoYkCJFIYPqz61voC2KpXGfnMCZSVlZmNkCV1d9Fy%2B1HH8ZMVBdBpiSXUlynGUz3UsOUEkVsOHjkno7tBv5bB0%2BmrEwxr1E3fhUWUC7LALDHMuSuUN6ukUeaWllwvrkgFWWWlz0cR1%2FRpoCyzXeR5qjrEelvLgU6%2Bjpf5jwE4OkSisIFL5ILNZwyGtMHtwgyEGSoX42sVzcAwKTRUWQlDYzR%2BX0dmqIPYM8S0hTK0uQIb6%2BzG7BEpy5WA9dWAcGTVXpMGCdPFuCj9Kg%3D%3D&sign_type=RSA2&timestamp=2020-07-24+21%3A41%3A28&version=1.0",
        "payCallbackInfo": null
    }
}
        
```






