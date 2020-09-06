# 商城首页

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

商城首页相关借口

## 产品说明



## 关键流程说明

## 接口说明




#### 1.1 获取首页数据接口

##### 接口说明

首页数据

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /home/index |

#####  输入参数
无

#####  错误说明


#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
         "defaultKeyword": {  //默认搜索词
            "id": 6, //id
            "userId": null, //用户ID
            "keyword": "520元礼包抢先领", //关键词
            "from": null //涞源
        },
        "banner": [  //广告
            {
                "id": 2, //id
                "url": "http://yanxuan.nosdn.127.net/bff2e49136fcef1fd829f5036e07f116.jpg", //图片
                "link": "", //跳转
                "content": "活动 美食节", // 描述
                "type": 1, //跳转类型 0 h5（取link跳转）  1 产品  2 活动
                "idValue": 1110016,  // 1: 对应产品ID  2: 对应活动ID
                "extParams": null
                
            }
        ],
        "daySelectList": [ //每日优选
            {
                "id": 5,   //id
                "imageUrl": "http://yanxuan.nosdn.127.net/ 65091eebc48899298171c2eb6696fe27.jpg", //图片
                "content": "测试", //描述
                "addTime": null, //添加时间
                "goodsId": 1006002 //产品ID
            }
        ],
        "couponList": [  //优惠券
            {
                "id": 9,  //id
                "name": "测试一下", //名称
                "desc": "",  //描述
                "tag": "", //标签
                "total": null, //总量
                "discount": 0.00, //优惠金额
                "min": 100.00, //最小使用金额
                "limit": null, //限制
                "type": null, //优惠券赠送类型，如果是0则通用券，用户领取；如果是1，则是注册赠券；如果是2，则是优惠券码兑换；
                "goodsType": null, //商品限制类型，如果0则全商品，如果是1则是类目限制，如果是2则是商品限制。
                "startTime": null,  //使用券开始时间
                "endTime": null,  //使用券截止时间
                "addTime": null,
                "imageUrl": null //图片
                "own":false //是否已拥有
            }
        ],
        "categoryList": [  //品类
            {
                "id": 1005000,  //类别ID
                "name": "居家" //类别名称
            }
        ],
        "goodsList": {  //产品信息
            "pageSize": 10,  //单页条数
            "total": 5,  //总条数
            "currentPage": 1,  //当前页
            "list": [
                {
                    "id": 1006002,  //产品id
                    "name": null, //名称
                    "tags": [], //数组
                    "picUrl": "http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png",  //图片
                    "unit": null,  //单位
                    "counterPrice": 919.00,  //专柜价
                    "retailPrice": 899.00, //销售价
                    "vipPrice": null, //会员价
                    "brief": null  //运营描述
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
            "nextPage": 1,
            "previousPage": 1,
            "totalPages": 1,
            "startIndex": 0,
            "firstPage": true,
            "lastPage": true,
            "empty": false
        }
    }
}
```


#### 1.2 今日推荐分页拉取

##### 接口说明

首页每日优选，拉取更多

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /day_selected/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
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



#### 1.3 溯源接口

##### 接口说明

溯源产品

##### 请求说明

| http 请求方式          | get/post     |
|:------------- |:---------------:|
| url      | /home/tracing |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| data      | 是|  string  |  二维码内容  |  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "tracingResult": [
            {
                "label": "身份唯一码",
                "value": "2022307987285385"
            },
            {
                "label": "产品名称",
                "value": "庆沣祥•白莺山春古茶（2016）"
            },
            {
                "label": "规格",
                "value": "357g/片"
            },
            {
                "label": "成品生产日期",
                "value": "2016年4月1日"
            },
            {
                "label": "出品公司",
                "value": "昆明七彩云南庆沣祥茶业股份有限公司"
            },
            {
                "label": "生产厂/监制人",
                "value": "勐海七彩云南茶厂有限公司/罗翔辉"
            },
            {
                "label": "仓储信息",
                "value": "2016年6月入七彩云南陈华仓"
            },
            {
                "label": "检验报告编号",
                "value": "Y142016-WB00196"
            },
            {
                "label": "检验机构",
                "value": "国家普洱茶产品质量监督检验中心"
            },
            {
                "label": "检验指标及检验情况",
                "value": "1.重金属—合格   2.农残—合格"
            },
            {
                "label": "原料来源",
                "value": "   精选普洱茶核心产区白莺山古茶园树龄百年以上的云南大叶种晒青毛茶原料，古法精制而成。"
            }
        ],
        "goods": {
            "id": 1181000,
            "name": "母亲节礼物-舒适安睡组合",
            "picUrl": "http://yanxuan.nosdn.127.net/1f67b1970ee20fd572b7202da0ff705d.png",
            "unit": "件",
            "counterPrice": 0.09,
            "retailPrice": 0.01,
            "vipPrice": 0.01,
            "brief": "安心舒适是最好的礼物",
            "gallery": [
                "http://yanxuan.nosdn.127.net/355efbcc32981aa3b7869ca07ee47dac.jpg",
                "http://yanxuan.nosdn.127.net/43e283df216881037b70d8b34f8846d3.jpg",
                "http://yanxuan.nosdn.127.net/12e41d7e5dabaf9150a8bb45c41cf422.jpg",
                "http://yanxuan.nosdn.127.net/5c1d28e86ccb89980e6054a49571cdec.jpg"
            ],
            "videos": null,
            "tags": null
        },
        "daySelectList": null
    }
}

```







