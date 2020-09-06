# 搜索相关接口

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

活动相关接口

## 产品说明



## 关键流程说明

## 接口说明






#### 1.0 活动主页

##### 接口说明

活动主页

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /promotion/index |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| page      | 否|  int  |  分页  | 默认1  |
| limit      | 否|  int  |  限制单页条数  | 默认10  |


#####  错误说明


#####  返回实例
```json

{
    "c": 0,
    "m": null,
    "d": {
        "banner": [
            {
                "id": 2, //id
                "url": "http://yanxuan.nosdn.127.net/bff2e49136fcef1fd829f5036e07f116.jpg", //图片
                "link": "", //跳转
                "content": "活动 美食节", // 描述
                "type": 1, //跳转类型 0 h5（取link跳转）  1 产品  2 活动
                "idValue": 1110016,  // 1: 对应产品ID  2: 对应活动ID
                "extParams": null  //附加自定义参数 json 格式 
            }
        ],
        "topics": {  //话题
            "pageSize": 10,
            "currentPage": 1,
            "list": [
                {
                    "goodsList": [   //产品列表
                        {
                            "id": 1006002, //产品ID
                            "name": "轻奢纯棉刺绣水洗四件套", //产品名称
                            "tags": null, //产品标签
                            "picUrl": "http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png", //产品图片
                            "unit": "件", //单位
                            "counterPrice": 919.00, //专柜价
                            "retailPrice": 899.00, //销售价
                            "vipPrice": 100000.00, //会员价
                            "brief": "设计师原款，精致绣花", //简介
                            "gallery": null, //图片列表
                            "videos": null //视频列表
                        }
                    ],
                    "title": "关爱他成长的每一个足迹", //标题
                    "subtitle": "专业运动品牌同厂，毛毛虫鞋买二送一", //子标题
                    "price": 0.00, //最低价
                    "readCount": "6.4k", //已读数
                    "picUrl": "https://yanxuan.nosdn.127.net/14943267735961674.jpg", //头图
                    "sortOrder": 1,  //排序字段
                    "addTime": "2018-02-01 00:00:00" //创建时间
                }
            ],
            "end": true,
            "startIndex": 0,
            "empty": false
        }
    }
}    

```



#### 1.1 活动主题分页查询

##### 接口说明

活动主题分页查询

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /promotion/list |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  page      | 否|  int  |  页码 | 默认第一页 |
|  limit      | 否|  int  |  单页条数|  默认10条 |

#####  错误说明


无


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
                "goodsList": [   //产品列表
                    {
                        "id": 1006002, //产品ID
                        "name": "轻奢纯棉刺绣水洗四件套", //产品名称
                        "tags": null, //产品标签
                        "picUrl": "http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png", //产品图片
                        "unit": "件", //单位
                        "counterPrice": 919.00, //专柜价
                        "retailPrice": 899.00, //销售价
                        "vipPrice": 100000.00, //会员价
                        "brief": "设计师原款，精致绣花", //简介
                        "gallery": null, //图片列表
                        "videos": null //视频列表
                    }
                ],
                "title": "关爱他成长的每一个足迹", //标题
                "subtitle": "专业运动品牌同厂，毛毛虫鞋买二送一", //子标题
                "price": 0.00, //最低价
                "readCount": "6.4k", //已读数
                "picUrl": "https://yanxuan.nosdn.127.net/14943267735961674.jpg", //头图
                "sortOrder": 1,  //排序字段
                "addTime": "2018-02-01 00:00:00" //创建时间
            }
        ],
        "end": true,
        "startIndex": 0,
        "empty": false
    }
    
}    

```



#### 1.2 活动详情

##### 接口说明

根据ID查询活动详情

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /topic/detail |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
|  id      | 是 |  int  |  主题ID |  |


#####  错误说明


无


#####  返回实例
```json

{
    "c": 0,
    "m": null,
    "d": {
        "goods": [
            {
                "id": 1006002, //产品ID
                "name": "轻奢纯棉刺绣水洗四件套", //产品名称
                "tags": null, //产品标签
                "picUrl": "http://yanxuan.nosdn.127.net/8ab2d3287af0cefa2cc539e40600621d.png", //产品图片
                "unit": "件", //单位
                "counterPrice": 919.00, //专柜价
                "retailPrice": 899.00, //销售价
                "vipPrice": 100000.00, //会员价
                "brief": "设计师原款，精致绣花", //简介
                "gallery": null, //图片列表
                "videos": null //视频列表
            }
        ],
        "topic": {
            "id": 264, //话题ID
            "title": "设计师们推荐的应季好物",  //标题
            "subtitle": "原创设计春款系列上新", //副标题
            "price": 29.90, //最低价
            "readCount": "77.7k", //已读数
            "picUrl": "https://yanxuan.nosdn.127.net/ 14918201901050274.jpg", //图片
            "sortOrder": 0, //排序
            "goods": [
                1006002
            ],
            "addTime": "2018-02-01 00:00:00", //添加时间
            "updateTime": "2018-02-01 00:00:00", //更新时间
            "deleted": false,
            "content": "<p></p>" //富文本内容
        }
    }
}  

```











