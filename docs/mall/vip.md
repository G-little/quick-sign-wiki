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
| url      | /vip/my |

#####  输入参数

无


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "uid": 11446,  //用户ID
        "avatar": "https://wx.qlogo.cn/mmopen/vi_32/DYAIOgq83eqDw87BjTffT03d4T5z9ynn6bia79vWUdDzXbvvCrhbL5oBAYIOTe6iaH790uto7CTkH71oDEpzuMjQ/132",
        "name": "杜京亚",
        "gender": 1,
        "birthday": null,
        "status": 0,
        "mobile": null,
        "createTime": 1593445700769,
        "updateTime": null,
        "vipStartTime": null,   //vip 开始时间
        "vipEndTime": null,  //vip 结束时间
        "userSource": null,  //用户来源
        "level": null,
        "vipTotalDays": null,  //用户vip 累计时长
        "buyTimes": null,  //累计购买次数
        "vipList": [
            {
                "id": 1,  //ID
                "comment": "一个月会员",  //描述
                "originalPrice": 300.00,  //原价
                "price": 2.00, //价格
                "timeLen": 1, //时长
                "timeType": 30, //时间类型 1:天 30:月
                "vipType": 0, // vip 类型
                "addTime": null, // 添加时间
                "delete": false, // 是否删除 
                "bgUrl": null //背景
            }
        ],   //vip 列表
        "payTypes": [
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
        "remainDays": 0,
        "vip": false
    }
}    
```



#### 1.0 vip 支付

##### 接口说明

vip 充值首页

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /vip/pay |

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
        "callPayInfo": "alipay_sdk=alipay-sdk-java-dynamicVersionNo&app_id=2019021963294014&biz_content=%7B%22out_trade_no%22%3A%22PRE20072323512323809B64E7981256%22%2C%22product_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22subject%22%3A%22%E4%B8%AD%E6%A0%87%E4%BC%98%E9%80%89%22%2C%22timeout_express%22%3A%2230m%22%2C%22total_amount%22%3A%222.0%22%7D&charset=UTF-8&format=json&method=alipay.trade.app.pay&notify_url=http%3A%2F%2Fxiaogang.org.cn&sign=MpclAkitGsMgourGcRVj6xvbHfb%2FyFH12FIXRYiPeQr6OXR2EUGAII5nHv9bTvQwk2QId%2BMDOuKeCGl3SBPZjXzb7aYTA%2BMW%2BCHwrG3YSdfsXLxbRMTPi659W0s%2FHiGJr2q%2FUKT8YTSFtNTVovc0LulMNXQ8IW4bIvyyjPypxntaHpNr6xRCkAx4JveliZQ1y5rknI8hS8nyd985ddHHxX%2F2v5m%2B1P3bRJFvkfmVku0GHtDtaz65nTDMQasisin39eJuo%2BTHXpkPv82GMI%2F5EL%2BhSZ%2F7nkw51XMAE1sUcjyH9pNMwHmBjTpLvu1GBHWEc%2B4StyPQwb2rNxpKFKanJA%3D%3D&sign_type=RSA2&timestamp=2020-07-23+23%3A51%3A24&version=1.0",
        "payCallbackInfo": null
    }
}
        
```






