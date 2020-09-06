# 购物车相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

购物车相关接口

## 产品说明



## 关键流程说明

## 接口说明






#### 1.0 购物车商品总数

##### 接口说明

获取购物车商品总数

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /cart/goodscount |

#####  输入参数

无

#####  错误说明


#####  返回实例
```json
   
   {
    "c": 0,
    "m": null,
    "d": 0  //商品总数
} 
   
```


#### 1.1 商品加入购物车

##### 接口说明

加入商品到购物车

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/add |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  productId      | 是|  int  |  商品ID | |
|  number      | 是|  int  |  产品数量 | |
|  goodsId      | 是|  int  |  产品Id | |


#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": 1  //购物车商品总数
}

```


#### 1.1 商品加入购物车

##### 接口说明

加入商品到购物车

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/add |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  productId      | 是|  int  |  商品ID | |
|  number      | 是|  int  |  产品数量 | |
|  goodsId      | 是|  int  |  产品Id | |


#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": 1  //购物车商品总数
}

```


#### 1.2 立即购买

##### 接口说明

立即购买

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/fastadd |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  productId      | 是|  int  |  商品ID | |
|  number      | 是|  int  |  产品数量 | |
|  goodsId      | 是|  int  |  产品Id | |
|  addressId      | 否|  int  |  地址ID | |
|  couponId      | 否|  int  |  优惠券ID | |
|  userCouponId      | 否|  int  |  用户优惠券ID | |


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


#### 1.3 更新购物车商品信息

##### 接口说明

更新购物车内商品信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/update |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  id      | 是|  int  |  购物车ID | |
|  productId      | 是|  int  |  商品ID | |
|  number      | 是|  int  |  产品数量 | |
|  goodsId      | 是|  int  |  产品Id | |


#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": 1  //购物车ID
}

```


#### 1.3 修改勾选状态信息

##### 接口说明

修改购物车勾选状态信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/checked |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  productIds      | 是|  int[]  |  商品ID数组 | |
|  isChecked      | 是|  int  |  是否选中 | 1:选中 0:取消 |


#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "cartList": [  //购物车列表
            {
                "id": 11,  //购物车项ID
                "goodsId": 1057036, //产品ID
                "goodsSn": "1057036", //产品SN
                "goodsName": "日式纯色水洗亚麻抱枕", //产品名称
                "productId": 71, //商品ID
                "price": 79.00, //总价格
                "number": 3, //数量
                "specifications": [  //规格
                    "标准"
                ],
                "checked": true, //是否选中
                "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png",  //展示图
                "addTime": "2020-07-04 09:29:23", //添加时间
                "updateTime": "2020-07-04 09:29:23" //更新时间
            }
        ],
        "cartTotal": {   //统计信息
            "goodsCount": 3, //商品数量
            "goodsAmount": 237.00, //总价格
            "checkedGoodsCount": 3, //选中商品总数量
            "checkedGoodsAmount": 237.00 //选中商品总价格
        }
    }
}

```



#### 1.4 购物车详情

##### 接口说明

获取购物车详情信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/index |

#####  输入参数

无

#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "cartList": [  //购物车列表
            {
                "id": 11,  //购物车项ID
                "goodsId": 1057036, //产品ID
                "goodsSn": "1057036", //产品SN
                "goodsName": "日式纯色水洗亚麻抱枕", //产品名称
                "productId": 71, //商品ID
                "price": 79.00, //货品单价
                "vipPrice": 79.00, //会员价
                "number": 3, //数量
                "specifications": [  //规格
                    "标准"
                ],
                "checked": true, //是否选中
                "tags":[], //标签
                "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png",  //展示图
                "addTime": "2020-07-04 09:29:23", //添加时间
                "updateTime": "2020-07-04 09:29:23" //更新时间
            }
        ],
        "cartTotal": {   //统计信息
            "goodsCount": 3, //商品数量
            "goodsAmount": 237.00, //总价格
            "checkedGoodsCount": 3, //选中商品总数量
            "checkedGoodsAmount": 237.00 //选中商品总价格
        }
    }
}
```


#### 1.5 删除购物车商品

##### 接口说明

删除购物车商品

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/delete |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  productIds      | 是|  int[]  |  商品ID数组 | |

#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "cartList": [  //购物车列表
            {
                "id": 11,  //购物车项ID
                "goodsId": 1057036, //产品ID
                "goodsSn": "1057036", //产品SN
                "goodsName": "日式纯色水洗亚麻抱枕", //产品名称
                "productId": 71, //商品ID
                "price": 79.00, //总价格
                "number": 3, //数量
                "specifications": [  //规格
                    "标准"
                ],
                "checked": true, //是否选中
                "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png",  //展示图
                "addTime": "2020-07-04 09:29:23", //添加时间
                "updateTime": "2020-07-04 09:29:23" //更新时间
            }
        ],
        "cartTotal": {   //统计信息
            "goodsCount": 3, //商品数量
            "goodsAmount": 237.00, //总价格
            "checkedGoodsCount": 3, //选中商品总数量
            "checkedGoodsAmount": 237.00 //选中商品总价格
        }
    }
}
```



#### 1.6 购物车结算

##### 接口说明

结算购物车商品

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /cart/checkout |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  cartId      | 否|  int  |  购物车ID | 如果购物车商品ID是空，则下单当前用户所有购物车商品； 如果购物车商品ID非空，则只下单当前购物车商品。 |
|  addressId      | 否|  int  |收货地址ID | 如果收货地址ID是空，则查询当前用户的默认地址。  |
|  couponId      | 否|  int  |优惠券ID | 如果优惠券ID是空，则自动选择合适的优惠券。|
|  userCouponId      | 否|  int  |用户选择的优惠券ID ||
|  grouponRulesId      | 否|  int  |团购规则ID ||

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
        ],
    "wallet": {
        "couponCount": 0, //优惠券
        "redEnvelopCount": 0, //红包
        "giftCardCount": 0, //礼品卡
        "money": 44637.84, //余额
        "userPoints": 0 //用户积分
        }       
    },
    "vipDiscountAmount":22.22
    "employeeType":0, //0普通用户  1:农创客商户
}

```





