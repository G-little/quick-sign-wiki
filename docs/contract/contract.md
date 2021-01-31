# 合同管理

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年09月08日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

合同管理接口

## 产品说明



## 关键流程说明

## 接口说明



#### 1.0 创建合同

##### 接口说明

添加用户车辆

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /contract/add |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| carId      | 是| int|  车辆ID |  |
| name      | 是| string  | 名字 | |
| signDate   | 是 | string  | 签署日期 |  2020年09月09日 |
| valuation   | 是 | string  | 车辆估值 | 车辆估值 |
| signAddr   | 是 | string  |  北京市朝阳区望京街 |  |
| rentStart   | 是 | string  | 开始时间 |  yyyyMMddHHmm |
| rentEnd   | 是 | string  | 结束时间 |  yyyyMMddHHmm |
| returnDate   | 是 | string  | 归还日期 |  yyyyMMddHHmm |
| returnAddr   | 是 | string  | 归还地址 |  |
| rentDayMoney   | 是 | double  |日租金 | 单位(元)  |
| rentTotalMoney   | 否 | double  |总租金| 单位(元)  |
| rentPayType   | 是 | int  |支付方式 |  0 一次性支付 1 周期支付  |
| cycleType   | 否 | int  |周期支付方式 |  1天 2月 3季度 4半年 5年  |
| cycleMoney   | 否 | double  |周期支付金额 |  单位 元 |
| depositType   | 是 | int  | 押金类型 |  0 无押金   1押金 |
| carDepositMoney   | 否 | double  | 车辆押金 |  单位元 |
| violationDepositMoney   | 否 | double  | 违章押金 |  单位元 |
| payType   | 是 | string  | 支付方式 |   balance 余额支付 / WX_MP 微信小程序支付 |

#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
            "payOrderId":xxxx,//订单号
            "callPayInfo":xxxxx, //各平台对应支付信息 
       }
    }

```



#### 1.2 合同预览

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /contract/preview |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| carId      | 是| int|  车辆ID |  |
| name      | 否| string  | 名字 | |
| signDate   | 否 | string  | 签署日期 |  2020年09月09日 |
| valuation   | 否 | string  | 车辆估值 | 车辆估值 |
| signAddr   | 否 | string  |  北京市朝阳区望京街 |  |
| rentStart   | 否 | string  | 开始时间 |  yyyyMMddHHmm |
| rentEnd   | 否 | string  | 结束时间 |  yyyyMMddHHmm |
| returnDate   | 否 | string  | 归还日期 |  yyyyMMddHHmm |
| returnAddr   | 否 | string  | 归还地址 |  |
| rentDayMoney   | 否 | double  |日租金 | 单位(元)  |
| rentTotalMoney   | 否 | double  |总租金| 单位(元)  |
| rentPayType   | 否 | int  |支付方式 |  0 一次性支付 1 周期支付  |
| cycleType   | 否 | int  |周期支付方式 |  1天 2月 3季度 4半年 5年  |
| cycleMoney   | 否 | double  |周期支付金额 |  单位 元 |
| depositType   | 否 | int  | 押金类型 |  0 无押金   1押金 |
| carDepositMoney   | 否 | double  | 车辆押金 |  单位元 |
| violationDepositMoney   | 否 | double  | 违章押金 |  单位元 |


#####  错误说明






#####  返回实例

pdf 文件流


#### 1.3 保存草稿

##### 接口说明

保存合同草稿

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /contract/save |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| carId      | 是| int|  车辆ID |  |
| name      | 是| string  | 名字 | |
| signDate   | 是 | string  | 签署日期 |  2020年09月09日 |
| valuation   | 是 | string  | 车辆估值 | 车辆估值 |
| signAddr   | 是 | string  |  北京市朝阳区望京街 |  |
| rentStart   | 是 | string  | 开始时间 |  yyyyMMddHHmm |
| rentEnd   | 是 | string  | 结束时间 |  yyyyMMddHHmm |
| returnDate   | 是 | string  | 归还日期 |  yyyyMMddHHmm |
| returnAddr   | 是 | string  | 归还地址 |  |
| rentDayMoney   | 是 | double  |日租金 | 单位(元)  |
| rentTotalMoney   | 否 | double  |总租金| 单位(元)  |
| rentPayType   | 是 | int  |支付方式 |  0 一次性支付 1 周期支付  |
| cycleType   | 否 | int  |周期支付方式 |  1天 2月 3季度 4半年 5年  |
| cycleMoney   | 否 | double  |周期支付金额 |  单位 元 |
| depositType   | 是 | int  | 押金类型 |  0 无押金   1押金 |
| carDepositMoney   | 否 | double  | 车辆押金 |  单位元 |
| violationDepositMoney   | 否 | double  | 违章押金 |  单位元 |
| payType   | 是 | string  | 支付方式 |   balance 余额支付 / WX_MP 微信小程序支付 |


#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "id":"xxx"  //草稿ID  
    }
}

```



#### 1.4 结算页

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /contract/checkout |

#####  输入参数

无


#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "balance": 0, //剩余合同
        "price": 20.0, //合同单价
        "minPrice": 10.0 //合同最低价
    }
}

```


#### 1.5 合同预签页

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /contract/presign/{id} |

#####  输入参数

URL参数:

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是| int|  合同ID |  |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "id": 9, //合同ID
        "realname": "冷立纲", //真实姓名
        "avatar": null, //头像
        "title": "test", //title
        "status": 1, //状态 0:初始 1:待签署 2:已签署
        "expireTime": null
    }
}

```


#### 1.5 合同预签页

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /contract/detail/{id} |

#####  输入参数

URL参数:

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是| int|  合同ID |  |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "id": {
            "id": 10,
            "url": "http://quick-contract.oss-cn-beijing.aliyuncs.com/emg9bthg9yr7cx35nayi.pdf?Expires=1599833230&OSSAccessKeyId=LTAI4FzddSZr1XtviwXwEGzz&Signature=vfelRZ93HUM6xhyg82Ww0iHbk1o%3D",  //合同，有效期10分钟
            "expireTime": "2020-09-12 21:55:15", //过期时间24小时
            "status": 1 // 1 待签署 2 已签署 0 初始 -1 过期作废
        }
    }
}

```



#### 1.5 合同签署第一步验证码获取

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /contract/sign/{id}/step1 |

#####  输入参数

URL参数:

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是| int|  合同ID |  |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "flowId": "1427689130229263187" //流水
    }
}

```


#### 1.6 合同签署第二步

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /contract/sign/{id}/step2 |

#####  输入参数

URL参数:

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是| int|  合同ID |  |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        
    }
}

```




#### 1.7 合同管理

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /contract/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| showType      | 否| int|  显示类型 | 2:已签署,1:待签署,-1:已作废,3:草稿 |
| page      | 否| int|  分页 |  |
| limit      | 否| int|  单页条数 |  |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "currentPage": 1,
        "list": [
            {
                "carImages": [
                    "/a"
                ],
                "carBrand": "法拉利", //品牌
                "carModel": "458", //型号
                "carColor": "red", //颜色
                "carNum": "xxx", //车牌
                "partyARealname": "孙涛", //甲方
                "partyBRealname": "冷立纲", //乙方
                "name": "test", //合同名称
                "rentStart": "2020-09-07 15:00:00", //有效期 开始
                "rentEnd": "2020-09-11 22:07:37", //有效期 结束
                "status": 2, //合同状态  0:初始 1:待签署 2:已签署 -1 已过期
                "payStatus": 1, //支付状态 0 初始 1 成功
                "bindStatus": 1, //绑定状态 0 初始 1 成功
                "addTime": null, //添加时间
                "expireTime": null //失效时间
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": null
    }
}

```




#### 1.7 合同管理

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /contract/draft/detail/{id} |

#####  输入参数

URL参数:

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是 | int|  草稿ID | |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "rentDayMoney": 50.0,  //每日租金
        "rentTotalMoney": 100.0 //总租金,
        "cycleMoney": 50.0, //每日还款
        "carDepositMoney": 22.0, //押金
        "violationDepositMoney": 40.0, //违章押金
        "totalDepositMoney": 62.0, //总押金
        "rentStart": "202009071500", //开始时间
        "rentEnd": "202009071600", //结束时间
        "rentDays": 1, //租赁天数
        "returnDate": "202009071600", //归还日期
        "id": null, //草稿ID
        "name": "test", //合同名称
        "signDate": "2020年09月09日", //签署日期
        "signAddr": "北京市朝阳区望京街", //签署地点
        "returnAddr": "北京京师",  //归还地点
        "rentPayType": 1, //0 一次性支付 1 周期支付 
        "cycleType": 2, //周期支付方式:  1天 2月 3季度 4半年 5年 
        "depositType": 2, //押金类型  0 无押金  1押金
        "addTime": 1599652953545, //添加时间
        "detete": null, 
        "carImages": [  //车辆图片
            "/a"
        ],
        "carBrand": "法拉利", //品牌
        "carModel": "458", //型号
        "carValuation": "200万", //估值
        "carColor": "red", //颜色
        "carVin": "123456", //车辆识别号
        "carEngineNum": "22222", //引擎号
        "carNum": "xxx", //车牌号
        "carOilNum": "98#", //油号
    }
}

```


#### 1.8 发邮件

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /contract/mail/{id} |

#####  输入参数

URL参数:

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| email      | 是 | string |  电子邮箱 | |




#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        
    }
}

```



#### 1.9 我的签章

##### 接口说明

输出用户合同余额

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /seal/list |

#####  输入参数

无



#####  错误说明

1. 缺少必填的参数。




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "name":"签章名",
        "selaText":"aaaaaaxxcfsds", //图章base64编码
        "type":0 // 0 个人章 1 组织章
    }
}

```























