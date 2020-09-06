# 用户管理

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

后台用户管理相关接口

## 产品说明



## 关键流程说明

## 接口说明


#### 1.0 用户列表

##### 接口说明

管理中心用户列表

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /admin/user/list |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name      | 否|  strring  |  用户名  |   |
| uid      | 否|  int  |  用户ID  |   |
| mobile      | 否|  string  |  手机号  |   |
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
                "uid": 11452,
                "avatar": "https://wx.qlogo.cn/mmopen/vi_32/DYAIOgq83erWxMXolPylQhpDXp2ian7PBuoDRWGINpdHib4KRB1aQiahicibznMcyj7atEIw9HM98dTQW19xKAWicFog/132",
                "name": "狂奔的蜗牛",
                "gender": 1,    //性别 1:男  2:女  0:保密
                "birthday": null,
                "status": 0,
                "mobile": null,
                "createTime": 1595066012848,
                "updateTime": null,
                "vipStartTime": null,
                "vipEndTime": null,
                "userSource": null, //用户来源 APP:  应用  MINI: 小程序
                "level": null, //会员等级
                "vipTotalDays": null, //会员累计天数
                "vip": false //是否vip
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0
    }
}  
```



#### 1.1 会员管理

##### 接口说明

会员条件查询列表

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /admin/user/vip_list |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name      | 否|  strring  |  用户名  |   |
| uid      | 否|  int  |  用户ID  |   |
| mobile      | 否|  string  |  手机号  |   |
| vipStatus      | 否|  int  |  会员状态  |  0 全部 1 vip 2 已过期   |
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
                "uid": 11452,
                "avatar": "https://wx.qlogo.cn/mmopen/vi_32/DYAIOgq83erWxMXolPylQhpDXp2ian7PBuoDRWGINpdHib4KRB1aQiahicibznMcyj7atEIw9HM98dTQW19xKAWicFog/132",
                "name": "狂奔的蜗牛",
                "gender": 1,    //性别 1:男  2:女  0:保密
                "birthday": null,
                "status": 0,
                "mobile": null,
                "createTime": 1595066012848,
                "updateTime": null,
                "vipStartTime": null,
                "vipEndTime": null,
                "userSource": null, //用户来源 APP:  应用  MINI: 小程序
                "level": null, //会员等级
                "vipTotalDays": null, //会员累计天数
                "vip": false, //是否vip
                "buyTimes": 5 // 会员累计购买次数
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0
    }
}  
``` 



#### 1.1 用户足迹

##### 接口说明

用户足迹

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /admin/footprint/list |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name      | 否|  strring  |  用户名  |   |
| uid      | 否|  int  |  用户ID  |   |
| goodsId      | 否|  int  |  产品ID  |   |
| goodsName      | 否|  int  |  产品ID  |   |
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
                "id": 766,
                "userId": 11450,
                "goodsId": 1006002,
                "goodsName": "产品名称",
                "addTime": "2020-07-19 15:17:59",
                "updateTime": "2020-07-19 15:17:59",
                "deleted": false
            }
        ],
        "end": true,
        "empty": false,
        "startIndex": 0
    }
}
    
``` 




#### 1.2 员工管理

##### 接口说明

管理中心用户列表

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /admin/employee/list |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name      | 否|  strring  |  用户名  |   |
| uid      | 否|  int  |  用户ID  |   |
| mobile      | 否|  string  |  手机号  |   |
| employeeType      | 否|  int  |  员工类型  |   1 中标优选 |
| page      | 否|  int  |  分页  | 默认1  |
| limit      | 否|  int  |  限制单页条数  | 默认10  |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
        "total": 15,
        "list": [
            {
                "uid": 11462, //用户ID
                "avatar": null, //头像
                "name": null, // 昵称
                "createTime": 1595935404952, //创建时间
                "mobile": "15201008963",//手机号
                "employeeType": "", //员工类型
                "money": null,  //余额
                "lastChargeMoney": null, //最后充值金额
                "lastChargeTime": null //最后充值时间
            }
        ],
        "pageNum": 1,
        "pageSize": 10,
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
    }
}
    
```


#### 1.3 添加员工

##### 接口说明

管理中心用户列表

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /admin/employee/create |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| name      | 是|  strring  |  用户名  |   |
| mobile      | 是|  string  |  手机号  |   |
| employeeType      | 否|  int  |  员工类型  |   1 中标优选 |


#####  错误说明




#####  返回实例
```json
    
    {
    "c": 0,
    "m": null,
    "d": {
       "id":152 //用户ID
    }
}
    
```


#### 1.4  员工充值

##### 接口说明

管理中心用户列表

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /admin/employee/transfer |

#####  输入参数


| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| uidList      | 是|  int[]  |  用户列表  |   |
| money      | 是|  double  |  转账金额 |   |
| reason      | 是|  string  |  转账说明 |   |


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














