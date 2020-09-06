# 产品相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

优惠券相关接口

## 产品说明



## 关键流程说明

## 接口说明

#### 1.0 分类获取商品信息

##### 接口说明

按商品类别分页拉取商品列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /goods/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| categoryId      | 否|  int  |  分类ID  |  0 为精选 |
| brandId      | 否|  int  |  品牌ID  |   |
| keyword      | 否|  string  |  查询关键词  |   |
| isNew      | 否|  boolean  |  是否新  |   |
| isHot      | 否|  boolean  |  是否热门  |   |
| sort      | 否|  string  |  排序字段  | add_time, retail_price, name|
| order      | 否|  string  |  倒序/正序  | asc  desc|
| page      | 否|  int  |  页码  | 默认值 1 |
| limit      | 否|  int  |  单页条数  | 默认值 10 |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "total": 1,
        "currentPage": 1,
        "list": [
            {
                "id": 1006002,  //产品ID
                "name": "轻奢纯棉刺绣水洗四件套", //名称
                "tags": null,  //标签
                "picUrl": "http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png",
                "unit": "件", //单位
                "counterPrice": 919.00,  //专柜价
                "retailPrice": 899.00, //零售价
                "vipPrice": 100000.00, //会员价
                "brief": "设计师原款，精致绣花", //简介
                "gallery":["http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png"], //图片
                "videos":[
                        {
                            "url":"/xxxx",
                            "cover":"cover",
                            "size":"x*y"
                        }
                    ]
            }
        ],
        "unit": "条",
        "extInfo": null,
        "endIndex": 10,
        "startIndex": 0,
        "firstPage": true,
        "lastPage": true,
        "nextPage": 1,
        "previousPage": 1,
        "totalPages": 1,
        "empty": false
    }
}

```


#### 1.1 商品详情信息

##### 接口说明

根据产品ID获取产品详细信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /goods/detail |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是|  int  |  产品ID  |  |


#####  错误说明




#####  返回实例
```json
    
   {
    "c": 0,
    "m": null,
    "d": {
        "defaultAddress": {  //默认收货地址
            "id": 3,
            "name": "我",
            "userId": 11445,
            "province": "北京市",
            "city": "市辖区",
            "county": "朝阳区",
            "addressDetail": "211",
            "areaCode": "110105",
            "postalCode": null,
            "tel": "15201008961",
            "isDefault": true,
            "addTime": "2020-06-29 14:46:15",
            "updateTime": "2020-06-29 14:46:15",
            "deleted": false
        },
        "couponList": [ //可用优惠券列表
            {
                "id": 2,
                "cid": null,
                "name": "限时满减券",
                "desc": "全场通用",
                "tag": "无限制",
                "min": 99.00,
                "discount": 10.00,
                "startTime": null,
                "endTime": null,
                "available": false,
                "reducedMoney": 10.00
            }
        ]
        "info": {
            "id": 1057036, //产品ID
            "goodsSn": "1057036", //产品SN
            "name": "日式纯色水洗亚麻抱枕", //品名
            "categoryId": 1008002, //品类
            "brandId": 1001000, //商标
            "gallery": [   //商品图片
                "http://yanxuan.nosdn.127.net/bec107bf0cc86dcf90fa084584d68c76.jpg"
            ],
            "keywords": "", //关键词
            "brief": "水洗亚麻，透气亲肤", //简介
            "isOnSale": true, //是否在售
            "sortOrder": 6, //排序
            "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png",  //缩略图
            "shareUrl": "",
            "isNew": false,  //是否新品
            "isHot": false, //是否热门
            "unit": "件", //单位
            "counterPrice": 99.00, //专柜价
            "retailPrice": 79.00, //销售价
            "vipPrice": 100000.00, //vip价格
            "addTime": "2018-02-01 00:00:00", //添加时间
            "updateTime": "2018-02-01 00:00:00", //更新时间
            "deleted": false,
            "detail": "", //富文本商品信息
            "tags": [],  //标签
            "videos": [],
            "testReports": []  //测试报告
        },
        "userHasCollect": 0,  //是否已收藏
        "issue": {  //常见问题
            "total": 0,
            "list": [
                {
                    "id": 1,
                    "question": "购买运费如何收取？",
                    "answer": "单笔订单金额（不含运费）满88元免邮费；不满88元，每单收取10元运费。\n(港澳台地区需满",
                    "addTime": "2018-02-01 00:00:00",
                    "updateTime": "2018-02-01 00:00:00",
                    "deleted": false
                },
                {
                    "id": 2,
                    "question": "使用什么快递发货？",
                    "answer": "严选默认使用顺丰快递发货（个别商品使用其他快递），配送范围覆盖全国大部分地区（港澳台地区除",
                    "addTime": "2018-02-01 00:00:00",
                    "updateTime": "2018-02-01 00:00:00",
                    "deleted": false
                },
                {
                    "id": 3,
                    "question": "如何申请退货？",
                    "answer": "1.自收到商品之日起30日内，顾客可申请无忧退货，退款将原路返还，不同的银行处理时间不同，",
                    "addTime": "2018-02-01 00:00:00",
                    "updateTime": "2018-02-01 00:00:00",
                    "deleted": false
                },
                {
                    "id": 4,
                    "question": "如何开具发票？",
                    "answer": "1.如需开具普通发票，请在下单时选择“我要开发票”并填写相关信息（APP仅限2.4.0及以",
                    "addTime": "2018-02-01 00:00:00",
                    "updateTime": "2018-02-01 00:00:00",
                    "deleted": false
                }
            ],
            "pageNum": 0,
            "pageSize": 0,
            "size": 0,
            "startRow": 0,
            "endRow": 0,
            "pages": 0,
            "prePage": 0,
            "nextPage": 0,
            "isFirstPage": false,
            "isLastPage": false,
            "hasPreviousPage": false,
            "hasNextPage": false,
            "navigatePages": 0,
            "navigatepageNums": null,
            "navigateFirstPage": 0,
            "navigateLastPage": 0
        },
        "comment": {  // 评论
            "count": 0, // 总数
            "data": [] // 评论数据
        },
        "specificationList": [  //商品规格列表
            {
                "name": "规格",  //规格名
                "valueList": [  //规格值
                    {
                        "id": 70,  //规格ID
                        "goodsId": 1057036, //产品ID
                        "specification": "规格", //规格名
                        "value": "标准",  //规格值
                        "picUrl": "", //规格图片
                        "addTime": "2018-02-01 00:00:00", //添加时间
                        "updateTime": "2018-02-01 00:00:00", //更新时间
                        "deleted": false //删除
                    }
                ]
            }
        ],
        "productList": [  //产品列表
            {
                "id": 71,  //商品ID
                "goodsId": 1057036, // 产品ID
                "specifications": [  //规格列表
                    "标准"
                ],
                "price": 79.00,  //价格
                "number": 96, //剩余总数
                "url": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png",  //规格图片
                "addTime": "2018-02-01 00:00:00", //添加时间
                "updateTime": "2020-06-20 17:31:29", //更新时间
                "deleted": false
            }
        ],
        "attribute": [   //产品属性
            {
                "id": 259,  //属性ID
                "goodsId": 1057036, //产品ID
                "attribute": "尺寸", //属性名
                "value": "45*45cm",//属性值
                "addTime": "2018-02-01 00:00:00",  //添加时间
                "updateTime": "2018-02-01 00:00:00" //更新时间
                "deleted": false
            },
            {
                "id": 260,
                "goodsId": 1057036,
                "attribute": "颜色",
                "value": "灰紫/ 蓝色/ 灰色/ 咖色",
                "addTime": "2018-02-01 00:00:00",
                "updateTime": "2018-02-01 00:00:00",
                "deleted": false
            }
        ],
        "keyIndicators": [  //关键指标
            {
                "id": 1,
                "goodsId": 1057036,
                "name": "无机砷",  //检测箱
                "unit": "mg/kg", //单位
                "value": "无", //值
                "deleted": false, //删除状态
                "limited": "0.05", //限定值
                "addTime": null, //添加时间 
                "updateTime": null //更新时间
            }
        ],
        
        "brand": {  //品牌信息
            "id": 1001000, //品牌ID
            "name": "MUJI制造商", //品牌名称
            "desc": "严选精选了MUJI制造商和生产原料，\n用几乎零利润的价格，剔除品牌溢价，\n让用户享受原品牌的品质生活。", //品牌描述
            "picUrl": "http://yanxuan.nosdn.127.net/1541445967645114dd75f6b0edc4762d.png",  //图片信息
            "sortOrder": 2, //排序
            "floorPrice": 12.90, //商品低价
            "addTime": "2018-02-01 00:00:00",
            "updateTime": "2018-02-01 00:00:00",
            "deleted": false
        },
        "groupon": [],
        "share": false,
        "shareImage": "" //分享图
    }
}

```


#### 1.2 相关商品推荐

##### 接口说明

相关商品推荐

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /goods/related |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是|  int  |  产品ID  |  |



#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 6,
        "total": 6,
        "currentPage": 1,
        "list": [
            {
                "id": 1057036, //产品ID
                "name": "日式纯色水洗亚麻抱枕", //产品名称
                "tags": null, //产品标签
                "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png", //产品Url
                "unit": "件", //单位
                "counterPrice": 99.00, //专柜价格
                "retailPrice": 79.00, //销售价格
                "vipPrice": 100000.00, //vip 价格
                "brief": "水洗亚麻，透气亲肤", //运营简介
                       "gallery":["http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png"], //图片
                "videos":[
                        {
                            "url":"/xxxx",
                            "cover":"cover",
                            "size":"x*y"
                        }
                    ]
            }
        ],
        "unit": "条",
        "extInfo": null,
        "empty": false,
        "endIndex": 6,
        "startIndex": 0,
        "firstPage": true,
        "lastPage": true,
        "nextPage": 1,
        "previousPage": 1,
        "totalPages": 1
    }
}
    
```




#### 1.3 产品规格库存信息（购物车弹出规格修改）

##### 接口说明

产品规格库存信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /goods/spec_store |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id      | 是|  int  |  产品ID  |  |



#####  错误说明




#####  返回实例


``` json


{
    "c": 0,
    "m": null,
    "d": {
        "specificationList": [  //商品规格列表
            {
                "name": "规格",  //规格名
                "valueList": [  //规格值
                    {
                        "id": 70,  //规格ID
                        "goodsId": 1057036, //产品ID
                        "specification": "规格", //规格名
                        "value": "标准",  //规格值
                        "picUrl": "", //规格图片
                        "addTime": "2018-02-01 00:00:00", //添加时间
                        "updateTime": "2018-02-01 00:00:00", //更新时间
                        "deleted": false //删除
                    }
                ]
            }
        ],
        "productList": [  //产品列表
            {
                "id": 71,  //商品ID
                "goodsId": 1057036, // 产品ID
                "specifications": [  //规格列表
                    "标准"
                ],
                "price": 79.00,  //价格
                "number": 96, //剩余总数
                "url": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png",  //规格图片
                "addTime": "2018-02-01 00:00:00", //添加时间
                "updateTime": "2020-06-20 17:31:29", //更新时间
                "deleted": false
            }
    }
}

```



#### 1.4 根据订单ID推荐相关产品

##### 接口说明

相关商品推荐

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /goods/order_related |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| orderId      | 是|  int  |  产品ID  |  |



#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 6,
        "total": 6,
        "currentPage": 1,
        "list": [
            {
                "id": 1057036, //产品ID
                "name": "日式纯色水洗亚麻抱枕", //产品名称
                "tags": null, //产品标签
                "picUrl": "http://yanxuan.nosdn.127.net/8a9ee5ba08929cc9e40b973607d2f633.png", //产品Url
                "unit": "件", //单位
                "counterPrice": 99.00, //专柜价格
                "retailPrice": 79.00, //销售价格
                "vipPrice": 100000.00, //vip 价格
                "brief": "水洗亚麻，透气亲肤", //运营简介
                       "gallery":["http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png"], //图片
                "videos":[
                        {
                            "url":"/xxxx",
                            "cover":"cover",
                            "size":"x*y"
                        }
                    ]
            }
        ],
        "unit": "条",
        "extInfo": null,
        "empty": false,
        "endIndex": 6,
        "startIndex": 0,
        "firstPage": true,
        "lastPage": true,
        "nextPage": 1,
        "previousPage": 1,
        "totalPages": 1
    }
}
    
```





#### 1.5 评价列表接口

##### 接口说明

分页拉取评价列表信息

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /comment/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| type      | 是|  int  |  类型  | 如果是0，则查询商品评论；如果是1，则查询活动评论  |
| valueId      | 是|  int  |  商品或活动ID  | 根据type 决定 |
| showType      | 是|  int  |  显示类型  |  如果是0 则是全部 1 有图片的 |
| page      | 否|  int  |  分页  |  |
| limit      | 否|  int  |  单页条数  |  |



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
                "addTime": "2020-08-05 00:15:47",
                "content": "？？",
                "adminContent": "",
                "picList": null,
                "userInfo": {
                    "uid": 11460,
                    "nickname": "狂奔的蜗牛",
                    "avatar": "https://wx.qlogo.cn/mmopen/vi_32/DYAIOgq83eoia7J3Cibw8mJ3rBT7GGrecWfr8SJFqEQKpafEWe9aPMtKhYvf2JEC01uw6ykPdwEag47QSthSSdNg/132"
                }
            },
            {
                "addTime": "2020-08-04 22:59:23",
                "content": "12345",
                "adminContent": "",
                "picList": [
                    {
                        "url": "yj59vj7talfir8vi76gp.jpg",
                        "type": "jpg/jpeg"
                    },
                    {
                        "url": "v29c241slystgxakiodn.jpg",
                        "type": "jpg/jpeg"
                    }
                ],
                "userInfo": {
                    "uid": 11460,
                    "nickname": "狂奔的蜗牛",
                    "avatar": "https://wx.qlogo.cn/mmopen/vi_32/DYAIOgq83eoia7J3Cibw8mJ3rBT7GGrecWfr8SJFqEQKpafEWe9aPMtKhYvf2JEC01uw6ykPdwEag47QSthSSdNg/132"
                }
            }
         ],
        "end": true,
        "empty": false,
        "startIndex": 0,
        "totalPage": 4
    }
}    
```






    
   





