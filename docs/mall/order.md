# 订单相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

订单相关接口

## 产品说明



## 关键流程说明

## 接口说明


#### 1.0 提交订单

##### 接口说明

提交订单并支付

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/submit |

#####  输入参数

_订单信息_

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| cartId      | 否|  int  |  购物车ID  |  只结算指定购物车结算项的产品，不填则结算所有选中产品 |
| addressId      | 否|  int  |  地理位置ID  |  不填则获取下面的地址信息建立地址 |
| couponId      | 否|  int  |  优惠券ID  |  指定使用的优惠券 |
| userCouponId      | 否|  int  |  用户优惠券ID  |  指定用户已领取的优惠券ID|
| message      | 否|  string  |  备注信息  |  |
| grouponRulesId      | 否|  int  |  团购规则ID  | 预留团购，暂时用不到 |
| grouponLinkId      | 否|  int  |  团购ID  | 预留团购，暂时用不到 |
| payType      | 是|  string  |  支付方式  |  根据结算页拉取的支付项填写，小程序可以固定写死 WX_MP|
| payType      | 是|  string  |  支付方式  |  根据结算页拉取的支付项填写，小程序可以固定写死 WX_MP|
| useIntegral      | 否|  long  |  使用积分数量  | |


_地址信息_ (若上面 addressId 为空，则地址信息为必填项)


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  name      | 是|  string  |  名称 | |
|  province      | 是|  string  |  省份 | |
|  city      | 是|  string  |  城市 | |
|  county      | 是|  string  |  乡 | |
|  addressDetail      | 是|  string  |  详细地址 | |
|  areaCode      | 是|  string  |  地址编码| |
|  postalCode      | 否|  string  |  邮政编码| |
|  tel      | 是|  string  |  电话 | |
|  isDefault      | 是|  boolean  | 是否默认地址 | |


#####  错误说明




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



#### 1.1 取消订单

##### 接口说明

根据订单ID获取订单详细信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/cancel |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |  订单详细信息  |  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
           
       }
    }

```


#### 1.2 支付订单

##### 接口说明

根据订单ID获取订单详细信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/prepay |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |  订单ID  |  订单号 |
| payType      | 是|  string  |  支付方式  |  根据结算页拉取的支付项填写，小程序可以固定写死 WX_MP|






#####  错误说明




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




#### 1.1 订单列表

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/list |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| showType      | 是|  int  |  订单列表  | 显示类型，0，全部订单； 1，待付款； 2，待发货； 3，待收货； 4，待评价。 5，已完成  |
| page      | 否|  int  |  分页  | 默认1  |
| limit      | 否|  int  |  限制单页条数  | 默认10  |






#####  错误说明




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
                "id": 5,  //订单ID
                "orderSn": "20200613513109",   //订单SN
                "actualPrice": 1998.00, //订单金额
                "orderStatusText": "已取消(系统)", //订单状态描述
                "handleOption": {
                    "cancel": false,  //是否可取消
                    "delete": true, //是否可删除
                    "pay": false, //是否可支付
                    "comment": false, //是否可评价
                    "confirm": false, //是否可确认收货
                    "refund": false, //是否可退货
                    "rebuy": false, //是否可重新购买
                    "aftersale": false  //是否可售后
                },
                "aftersaleStatus": 0,  //售后状态，0是可申请，1是用户已申请，2是管理员审核通过，3是管理员退款成功，4是管理员审核拒绝，5是用户已取消
                "goodsList": [], //产品列表
                "groupin": false  //是否团购
            }      
         ],
        "end": true,
        "startIndex": 0,
        "empty": false
    }
}
```




#### 1.2 订单详情

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/detail |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |






#####  错误说明




#####  返回实例
```json
    
{
    {
    "c": 0,
    "m": null,
    "d": {
        "orderInfo": {  //订单信息
            "id": 47, //订单ID
            "orderSn": "20200711391009", //订单sN
            "message": "", //留言
            "addTime": "2020-07-11 18:48:01", //添加时间
            "payTime": "2020-07-11 18:48:01", //支付时间
            "consignee": "string", //收货人
            "mobile": "15201008961", //手机号
            "address": "stringstringstring string",  //收货地址
            "goodsPrice": 78.00,  //产品价格
            "couponPrice": 0.00, //优惠券价格
            "freightPrice": 8.00, //运费
            "actualPrice": 86.00, //实际支付
            "orderStatusText": "未付款",  //付款状态描述
            "handleOption": {  //处理状态
                "cancel": true,  //是否可取消
                "delete": false, //是否可删除
                "pay": true,  //是否可支付
                "comment": false, //是否可评论
                "confirm": false,  //是否可确认收货
                "refund": false, //是否可退货
                "rebuy": false, //是否可重新购买
                "aftersale": false, //是否可售后
                "remind": false, //是否可催单
                "logistic": true //是否可查看物流
            },
            "aftersaleStatus": 0,  //售后状态，0是可申请，1是用户已申请，2是管理员审核通过，3是管理员退款成功，4是管理员审核拒绝，5是用户已取消
            "expCode": null, //物流公司编码
            "expName": null, //物流名称
            "expNo": null //物流单号
        },
        "orderGoods": [  //订单产品信息
            {
                "id": 47,  //产品ID
                "orderId": 47, //订单ID
                "goodsId": 1006014, //商品ID
                "goodsName": "双宫茧桑蚕丝被 子母被", //名称
                "goodsSn": "1006014", //SN
                "productId": 11, //货品ID
                "number": 1, //数量
                "price": 1399.00, //价格
                "specifications": [  //规格
                    "标准"
                ],
                "handleOption": {  //操作按钮
                    "apply": false, //申请售后
                    "hotline": false, //客服热线
                    "cancel": false //取消售后
                },
                "aftersaleId":123,//售后ID
                "picUrl": "http://yanxuan.nosdn.127.net/2b537159f0f789034bf8c4b339c43750.png",  //图片
                "comment": 0,  //评论数
                "addTime": "2020-07-11 11:39:02", //添加时间
                "updateTime": "2020-07-11 11:39:02", //更新时间
                "deleted": false //是否已删除
            }
        ],
        "expressInfo": {   //物流信息
            "state": "0",
            "success": true,
            "reason": "暂无轨迹信息",  //原因
            "logisticCode": "1234561", //快递号
            "shipperCode": "ZTO", //编码
            "traces": [],   //轨迹
            "ebusinessID": "1638638",  //厂商b
            "shipperName": "中通快递",  //快递名称
            "LogisticCode": "1234561",
            "ShipperCode": "ZTO",
            "Traces": [],
            "State": "0",
            "EBusinessID": "1638638",
            "Success": true,
            "Reason": "暂无轨迹信息"
        }
    }
}

```


#### 1.2 取消订单

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/cancel |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |






#####  错误说明




#####  返回实例
```json
    
{
    {
    "c": 0,
    "m": null,
    "d": {
       
    }
}

```



#### 1.3  重新支付订单

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/prepay |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |
| payType      | 是|  string  |   支付方式   |  根据结算页拉取的支付项填写，小程序可以固定写死 WX_MP |






#####  错误说明




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



#### 1.4  确认收货接口

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/confirm |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        	
       }
    }



```


#### 1.4  删除订单接口

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/delete |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        	
       }
    }



```



#### 1.5  评价接口

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/comment |

#####  输入参数(post json)


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderGoodsId      | 是|  int  |   订单商品ID  |  |
| content      | 是|  string  |  商品内容信息  |  |
| star      | 是|  int  |  评价星级  | 1-5  |
| picUrls      | 是|  string[]  |  图片信息  |  |


    
``` json    
    {
      "anonymous": true,  //是否匿名
      "content": "string", //内容
      "picUrls": [ //图片数组
        {
            "url":"http://www.baidu.com", //url
            "type":"jpg/jpeg" //内容类型(可能是视频)
        }
      ],
      "star": 0, //星级
      "type": 0,  //如果是0，则查询商品评论；如果是1，则查询专题
      "valueId": 0  //商品或专题ID。如果type是0，则是商品ID；如果type是1，则是专题ID
    }
```



#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        
    }
}

```



#### 1.6  待评价订单商品信息

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/goods |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "id": 47,
        "orderId": 47,
        "goodsId": 1006014, //产品ID
        "goodsName": "双宫茧桑蚕丝被 子母被", // 产品名称
        "goodsSn": "1006014", //产品SN
        "productId": 11, //商品ID
        "number": 1, // 计数
        "price": 1399.00, //商品价格
        "specifications": [  //规格
            "标准"
        ],
        "picUrl": "http://yanxuan.nosdn.127.net/2b537159f0f789034bf8c4b339c43750.png",  //图片
        "comment": 0, //订单商品评论，如果是-1，则超期不能评价；如果是0，则可以评价；如果其他值，则是comment表里面的评论ID。
        "addTime": "2020-07-11 11:39:02",  //添加时间
        "updateTime": "2020-07-11 11:39:02", //更新时间
        "deleted": false
    }
}

```




#### 1.7 催单接口

##### 接口说明

催单

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/remind |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |  订单详细信息  |  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
           
       }
    }

```



#### 1.8 重新购买

##### 接口说明

重新购买

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /order/rebuy |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |  订单详细信息  |  |


#####  错误说明




#####  返回实例
```json
    
   {
    "c": 0,
    "m": null,
    "d": {
        "addressId": 3,   //地址ID
        "couponId": 2, //优惠券ID
        "userCouponId": 5, //用户优惠券ID
        "cartId": 0, // 购物车ID
        "grouponRulesId": 0, //团购规则
        "grouponPrice": 0, //团购价
        "checkedAddress": {   //地址的选择
            "id": 3,  //地址ID
            "name": "我", //地址名称
            "userId": 11445, //用户ID
            "province": "北京市", //省
            "city": "市辖区", //市
            "county": "朝阳区", //朝阳
            "addressDetail": "211", //地址详情
            "areaCode": "110105", //地址编码
            "postalCode": null, //邮政编码
            "tel": "15201008961", //手机号
            "isDefault": true, //是否默认
            "addTime": "2020-06-29 14:46:15", //创建时间
            "updateTime": "2020-06-29 14:46:15", //更新时间
            "deleted": false //是否已删除
        },
        "availableCouponLength": 2, //可用优惠券数量
        "goodsTotalPrice": 237.00, //产品总价格
        "freightPrice": 0,  //运费
        "couponPrice": 10.00, //优惠金额
        "orderTotalPrice": 227.00, //订单总金额
        "actualPrice": 227.00, //实付金额 
        "checkedGoodsList": [  //结算商品列表
            {
                "id": 10,  //ID
                "userId": 11445, //用户ID
                "goodsId": 1057036, //产品ID
                "goodsSn": "1057036", //产品SN
                "goodsName": "日式纯色水洗亚麻抱枕", //产品名称
                "productId": 71, //商品ID
                "price": 79.00, //商品价格
                "number": 3, //商品数量
                "specifications": [  //规格
                    "标准"
                ],
                "checked": true, //是否选中
                "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png", //缩略图
                "addTime": "2020-07-03 23:11:14", //添加时间
                "updateTime": "2020-07-03 23:35:09", //更新时间
                "deleted": false //是否已删除
            }
        ],
    "payTypes": [  //支付方式列表
            {
                "typeName": "balance",
                "comment": "余额支付",
                "thumbnail": null
            },
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
        ]   
    }
}


```



#### 1.9 订单重新支付

##### 接口说明

订单列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /order/repay |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |   订单ID  |  |






#####  错误说明




#####  返回实例
```json
    
{
    {
    "c": 0,
    "m": null,
    "d": {
        "actualPrice":1.23, //实付金额
        "payTypes":[  //支付方式列表
            {
                "typeName": "balance",
                "comment": "余额支付",
                "thumbnail": null
            },
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
        ] 
    }
}

```













