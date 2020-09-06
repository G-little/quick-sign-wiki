# 商品管理

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

后台商品管理相关接口

## 产品说明



## 关键流程说明

## 接口说明


#### 1.0 创建商品

##### 接口说明

管理中心用户列表

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /admin/goods/update |

#####  输入参数


```json  

{
  "attributes": [   //商品参数
    {
      "attribute": "string",  //属性名
      "deleted": true, 是否删除
      "goodsId": 0, //产品ID
      "id": 0, //参数ID
      "value": "string" //参数值
    }
  ],
  "goods": {
    "brandId": 0,  //品牌
    "brief": "string", // 商品简介
    "categoryId": 0,  //商品分类
    "counterPrice": 0, // 标价
    "retailPrice": 0, // 售价（非必填，最终值为所有货品价格里的最低价格，若货品价格未填写，则货品价格同步售价）
    "vipPrice": 0,  //会员价（对应最低售价对应的会员价，若货品价格未填写，则货品价格同步该会员价）
    "deleted": true,  //是否删除
    "detail": [  //详情图片列表
      {
        "size": "string",  //图片尺寸（x*y） 宽*高
        "url": "string"  // 图片下载地址
      }
    ],
    "gallery": [  //商品宣传图片列表，采用JSON数组格式
      "string"  //图片下载地址
    ],
    "goodsSn": "string",  //商品SN编码
    "id": 0, //商品ID
    "isHot": true, //是否热门
    "isNew": true, //是否新品
    "isOnSale": true, //是否在售
    "keywords": "string", //关键词,逗号分隔
    "name": "string", //商品名称
    "picUrl": "string", //商品页面商品图片
    
    "shareUrl": "string", //商品分享海报
    "sortOrder": 0, //排序字断
    "tags": [  //标签
      {
        "name": "string",
        "type": 0,
        "url": "string"
      }
    ],
    "testReports": [  //测试报告
      {
        "size": "string", //图片尺寸
        "url": "string" // 图片下载地址
      }
    ],
    "unit": "string", //单位
    "videos": [   //视频
      {
        "cover": "string",  //封面
        "size": "string",  //宽*高
        "url": "string" //下载地址
      }
    ],
  },
  "specifications": [  //商品规格
    {
      "deleted": true,  //是否删除
      "goodsId": 0, //产品ID
      "id": 0,  //规格ID
      "picUrl": "string", //规格图片
      "specification": "string", //规格名
      "value": "string" //规格值
    }
  ],
  "products": [   //货品信息
    {
      "deleted": true,   //删除
      "goodsId": 0, //产品ID
      "id": 0, //货品ID
      "number": 0,  //库存
      "counterPrice": 0, // 标价
      "price": 0, // 售价（非必填，没填，则取商品售价，若两个都未填则报参数错误）
      "vipPrice": 0,  //会员价（非必填，没填，则取商品会员价，若两个都未填则报参数错误
      "specifications": [ //规格对应值
        "string"
      ],
      "url": "string"   //规格对应商品图片
    }
  ]
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



#### 1.0 更新商品

##### 接口说明

管理中心用户列表

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /admin/goods/create |

#####  输入参数


```json  

{
  "attributes": [   //商品参数
    {
      "attribute": "string",  //属性名
      "deleted": true, 是否删除
      "goodsId": 0, //产品ID
      "id": 0, //参数ID
      "value": "string" //参数值
    }
  ],
  "goods": {
    "brandId": 0,  //品牌
    "brief": "string", // 商品简介
    "categoryId": 0,  //商品分类
    "counterPrice": 0, // 标价
    "retailPrice": 0, // 售价（非必填，最终值为所有货品价格里的最低价格，若货品价格未填写，则货品价格同步售价）
    "vipPrice": 0,  //会员价（对应最低售价对应的会员价，若货品价格未填写，则货品价格同步该会员价）
    "deleted": true,  //是否删除
    "detail": [  //详情图片列表
      {
        "size": "string",  //图片尺寸（x*y） 宽*高
        "url": "string"  // 图片下载地址
      }
    ],
    "gallery": [  //商品宣传图片列表，采用JSON数组格式
      "string"  //图片下载地址
    ],
    "goodsSn": "string",  //商品SN编码
    "id": 0, //商品ID
    "isHot": true, //是否热门
    "isNew": true, //是否新品
    "isOnSale": true, //是否在售
    "keywords": "string", //关键词,逗号分隔
    "name": "string", //商品名称
    "picUrl": "string", //商品页面商品图片
    
    "shareUrl": "string", //商品分享海报
    "sortOrder": 0, //排序字断
    "tags": [  //标签
      {
        "name": "string",
        "type": 0,
        "url": "string"
      }
    ],
    "testReports": [  //测试报告
      {
        "size": "string", //图片尺寸
        "url": "string" // 图片下载地址
      }
    ],
    "unit": "string", //单位
    "videos": [   //视频
      {
        "cover": "string",  //封面
        "size": "string",  //宽*高
        "url": "string" //下载地址
      }
    ],
  },
  "specifications": [  //商品规格
    {
      "deleted": true,  //是否删除
      "goodsId": 0, //产品ID
      "id": 0,  //规格ID
      "picUrl": "string", //规格图片
      "specification": "string", //规格名
      "value": "string" //规格值
    }
  ],
  "products": [   //货品信息
    {
      "deleted": true,   //删除
      "goodsId": 0, //产品ID
      "id": 0, //货品ID
      "number": 0,  //库存
      "counterPrice": 0, // 标价
      "price": 0, // 售价（非必填，没填，则取商品售价，若两个都未填则报参数错误）
      "vipPrice": 0,  //会员价（非必填，没填，则取商品会员价，若两个都未填则报参数错误
      "specifications": [ //规格对应值
        "string"
      ],
      "url": "string"   //规格对应商品图片
    }
  ]
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





#### 1.1 更新商品

##### 接口说明

     * 编辑商品
     * <p>
     * NOTE： 由于商品涉及到四个表，特别是litemall_goods_product表依赖litemall_goods_specification表，
     * 这导致允许所有字段都是可编辑会带来一些问题，因此这里商品编辑功能是受限制： （1）litemall_goods表可以编辑字段；
     * （2）litemall_goods_specification表只能编辑pic_url字段，其他操作不支持；
     * （3）litemall_goods_product表只能编辑price, number和url字段，其他操作不支持；
     * （4）litemall_goods_attribute表支持编辑、添加和删除操作。
     * <p>
     * NOTE2: 前后端这里使用了一个小技巧： 如果前端传来的update_time字段是空，则说明前端已经更新了某个记录，则这个记录会更新；
     * 否则说明这个记录没有编辑过，无需更新该记录。
     * <p>
     * NOTE3: （1）购物车缓存了一些商品信息，因此需要及时更新。 目前这些字段是goods_sn, goods_name, price, pic_url。
     * （2）但是订单里面的商品信息则是不会更新。 如果订单是未支付订单，此时仍然以旧的价格支付。

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /admin/goods/update |

#####  输入参数


```json  

{
  "attributes": [   //商品参数
    {
      "attribute": "string",  //属性名
      "deleted": true, 是否删除
      "goodsId": 0, //产品ID
      "id": 0, //参数ID
      "value": "string" //参数值
    }
  ],
  "goods": {
    "brandId": 0,  //品牌
    "brief": "string", // 商品简介
    "categoryId": 0,  //商品分类
    "counterPrice": 0, // 标价
    "retailPrice": 0, // 售价（非必填，最终值为所有货品价格里的最低价格，若货品价格未填写，则货品价格同步售价）
    "vipPrice": 0,  //会员价（对应最低售价对应的会员价，若货品价格未填写，则货品价格同步该会员价）
    "deleted": true,  //是否删除
    "detail": [  //详情图片列表
      {
        "size": "string",  //图片尺寸（x*y） 宽*高
        "url": "string"  // 图片下载地址
      }
    ],
    "gallery": [  //商品宣传图片列表，采用JSON数组格式
      "string"  //图片下载地址
    ],
    "goodsSn": "string",  //商品SN编码
    "id": 0, //商品ID
    "isHot": true, //是否热门
    "isNew": true, //是否新品
    "isOnSale": true, //是否在售
    "keywords": "string", //关键词,逗号分隔
    "name": "string", //商品名称
    "picUrl": "string", //商品页面商品图片
    
    "shareUrl": "string", //商品分享海报
    "sortOrder": 0, //排序字断
    "tags": [  //标签
      {
        "name": "string",
        "type": 0,
        "url": "string"
      }
    ],
    "testReports": [  //测试报告
      {
        "size": "string", //图片尺寸
        "url": "string" // 图片下载地址
      }
    ],
    "unit": "string", //单位
    "videos": [   //视频
      {
        "cover": "string",  //封面
        "size": "string",  //宽*高
        "url": "string" //下载地址
      }
    ],
  },
  "specifications": [  //商品规格
    {
      "deleted": true,  //是否删除
      "goodsId": 0, //产品ID
      "id": 0,  //规格ID
      "picUrl": "string", //规格图片
      "specification": "string", //规格名
      "value": "string" //规格值
    }
  ],
  "products": [   //货品信息
    {
      "deleted": true,   //删除
      "goodsId": 0, //产品ID
      "id": 0, //货品ID
      "number": 0,  //库存
      "counterPrice": 0, // 标价
      "price": 0, // 售价（非必填，没填，则取商品售价，若两个都未填则报参数错误）
      "vipPrice": 0,  //会员价（非必填，没填，则取商品会员价，若两个都未填则报参数错误
      "specifications": [ //规格对应值
        "string"
      ],
      "url": "string"   //规格对应商品图片
    }
  ]
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












