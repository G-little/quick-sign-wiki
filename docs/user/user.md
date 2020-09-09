# 用户接口文档

[TOC]
## 修订记录
----
日期 | 作者 | 修订类型 | 修订内容 | 版本|
---- | ---- | ---- | ---- | ---- |
2020年07月03日|冷立纲|A|新增设计方案|1.0|

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

商城用户注册登录相关接口

## 产品说明



## 关键流程说明

## 接口说明

### 登录流程说明


#### 登录头说明

_将accessToken作为请求头 Authorization: 'token'  发送请求即可获取权限_

#### 手机号登录

1. 调用短信发送接口发送短信验证 /user/sendsms 
2. 手机号注册登录获取token /user/joinin 
3. 将accessToken作为请求头 Authorization: 'token'  发送请求

#### 微信登录

1. 微信授权回调接口 /oauth2/login_by_weixin 获取登录token
2. 将accessToken作为请求头 Authorization: 'token'  发送请求






#### 1.1 获取用户信息

##### 接口说明

登录后获取用户基本信息接口

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /user/get |

#####  输入参数

无

#####  错误说明




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "uid": 11443, //用户id
        "avatar": "/c/d/e", //用户头像
        "name": "赵六", //用户名
        "gender": 1, //性别
        "birthday": 153000000, //生日
        "status": 0,
        "mobile": "15201008961",//手机号
        "createTime": 1590149492786, //创建时间
        "updateTime": 1590149538735 //更新时间
    }
}

```


#### 1.2 退出登录

##### 接口说明

退出登录

##### 请求说明

| http 请求方式          | get     |
|:------------- |:---------------:|
| url      | /user/logout |

#####  输入参数

无

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


#### 1.3 修改用户信息

##### 接口说明

修改用户基本信息

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /user/update |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| avatar      | 否| string  |  头像 |  |
| birthday      | 否| int  | 生日 |   |
| gender   | 否 | int  | 性别 |   1:男  2:女  0:未知 |
| name   | 否 | string  | 姓名 | 用户名 |


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



#### 1.4 刷新token

##### 接口说明

刷新登录token

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /user/token/refresh |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| refreshToken      | 是| string  |  刷新token|   |


#####  错误说明




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "id": 88,
        "uid": 11443,  //用户id
        "deviceId": "A15201008961", //设备号
        "deviceType": 1, //设备类型
        "os": null, //操作系统
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOlsiMTE0NDMiLCJBMTUyMDEwMDg5NjEiXSwiZXhwIjoxNTk5MTAyOTY0fQ.0ShFRmKL1pLB9-Bq4vyOHxEvJWU0NqJT74STiA6RHoc",  //access token
        "accessExpiresIn": 1599102964223, // 失效时间
        "refreshToken": "enIuFVWofatzMTqEyg", //刷新token
        "refreshExpiresIn": 1604373364223, //刷新token失效时间
        "createTime": null,
        "updateTime": null,
        "pass": "tTofWxX" //解密密钥
    }
}

```



#### 1.5 微信小程序授权登录

##### 接口说明

刷新登录token

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /oauth2/login_by_weixin |

#####  输入参数

{
    "code":"xxxxx",
    "userInfo":{
        "nickName":"xxx",
        "avatarUrl":"xxx",
        "country":"xxx",
        "province":"xxx",
        "city":"xxx"
    }
}

#####  错误说明

**需要绑定手机号的情况**

```json 
    
    {
    "c":30002,
    "m":"需要绑定手机号",
    "d":{
        "key":"xxxxxx"
    }
    
}

```





#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "uid": 11443, //用户ID
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOlsiMTE0NDMiLCJBMTUyMDEwMDg5NjEiXSwiZXhwIjoxNTk5MDk4ODIzfQ.ng6CyFi4MTu-HtDRzffWpetApPrzM5z-JKv3a0t8v0g", //登录token
        "accessExpiresIn": 1599098823065, //失效时间
        "refreshToken": "fMYerhGCyudmIhLUW", //刷新token
        "refreshExpiresIn": 1604369223065, //刷新token 失效时间
        "user": { //用户信息
            "uid": 11443,  //用户ID
            "avatar": "/c/d/e", //用户头像
            "name": "赵六", //用户昵称
            "gender": 1, // 性别  1 男
            "birthday": 153000000, //生日
            "status": 0, //状态
            "mobile": "15201008961", //手机号
            "createTime": 1590149492786, //创建时间
            "updateTime": 1590149538735 //更新时间
        }
    }
}

```







#### 1.8 微信授权获取手机号

##### 接口说明

刷新登录token

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /oauth2/get_mobile_weixin |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| key      | 是| string  |  微信登录key |   |
| encryptedData      | 是| string  |  微信授权返回数据 |   |
| iv      | 是| string  |  微信授权返回数据 |   |


#####  错误说明




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
        "uid": 11443, //用户ID
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOlsiMTE0NDMiLCJBMTUyMDEwMDg5NjEiXSwiZXhwIjoxNTk5MDk4ODIzfQ.ng6CyFi4MTu-HtDRzffWpetApPrzM5z-JKv3a0t8v0g", //登录token
        "accessExpiresIn": 1599098823065, //失效时间
        "refreshToken": "fMYerhGCyudmIhLUW", //刷新token
        "refreshExpiresIn": 1604369223065, //刷新token 失效时间
        "user": { //用户信息
            "uid": 11443,  //用户ID
            "avatar": "/c/d/e", //用户头像
            "name": "赵六", //用户昵称
            "gender": 1, // 性别  1 男
            "birthday": 153000000, //生日
            "status": 0, //状态
            "mobile": "15201008961", //手机号
            "createTime": 1590149492786, //创建时间
            "updateTime": 1590149538735 //更新时间
        }
    }
}


```



#### 1.7 更新手机号接口step1

##### 接口说明

验证已有手机号

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /user/mobile/update/step1 |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile      | 是| string  |  手机号|   |
| smscode      | 是| string  |  验证码 |  /user/sendsms  interfaceType 5 发送 |


#####  错误说明




#####  返回实例
```json
    
{
    "c": 0,
    "m": null,
    "d": {
       "secret":"FnWVgshcWl"
    }
}

```



#### 1.8 更新手机号接口step2

##### 接口说明

验证已有手机号

##### 请求说明

| http 请求方式          | post     |
|:------------- |:---------------:|
| url      | /user/mobile/update/step2 |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile      | 是| string  |  手机号|   |
| smscode      | 是| string  |  验证码 |  /user/sendsms  interfaceType 2 发送 |
| secret      | 是| string  |  验证码 |  第一步验证手机返回|


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



#### 1.9 手机号快速登录

##### 接口说明

继承支付宝手机号认证快捷登录功能

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/user/xlogin |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| accessToken      | 是| string  |  sdk  获取的认证码 |   |
| deviceId      | 是| string  |  设备号 |   |
| deviceType      | 否| string  |  设备类型 |   1 手机  2 平板 3 pc 4 电脑|
| os      | 否| string  |  操作系统及版本 |  |

#####  错误说明

先整理可能的错误类型，具体对应的错误码实施时再确定：

1. 非法验证码



#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "uid": 11443, //用户ID
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdWQiOlsiMTE0NDMiLCJBMTUyMDEwMDg5NjEiXSwiZXhwIjoxNTk5MDk4ODIzfQ.ng6CyFi4MTu-HtDRzffWpetApPrzM5z-JKv3a0t8v0g", //登录token
        "accessExpiresIn": 1599098823065, //失效时间
        "refreshToken": "fMYerhGCyudmIhLUW", //刷新token
        "refreshExpiresIn": 1604369223065, //刷新token 失效时间
        "user": { //用户信息
            "uid": 11443,  //用户ID
            "avatar": "/c/d/e", //用户头像
            "name": "赵六", //用户昵称
            "gender": 1, // 性别  1 男
            "birthday": 153000000, //生日
            "status": 0, //状态
            "mobile": "15201008961", //手机号
            "createTime": 1590149492786, //创建时间
            "updateTime": 1590149538735 //更新时间
        }
    }
}
```



#### 1.10 获取实名认证验证码

##### 接口说明

3要素实名认证

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/user/realname/step1 |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| realname      | 是| string  |  姓名 |   |
| idcardNum      | 是| string  |  身份证号 |   |
| mobile      | 是| string  |  设备类型 |  手机号   |


#####  错误说明




#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "flowId": "1422815390941054682" 
    }
}

```



#### 1.11 实名认证手机号验证

##### 接口说明

3要素实名认证

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/user/realname/step2 |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| flowId      | 是| string  |  流水号 |   |
| smscode      | 是| string  |  验证码 |   |



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



#### 1.12 实名认证状态查询

##### 接口说明

3要素实名认证结果查询

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/user/realname/status |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| flowId      | 是| string  |  流水号 |   |



#####  错误说明




#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "status":false, //成功:true,失败:false
    }
}

```



#### 1.12 更新实名认证账户

##### 接口说明

更新实名认证的手机号，调用完更新后， 调用 /user/realname/step2 验证手机号验证码



##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/user/realname/update |

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile      | 是| string  |  更新手机号 |   |



#####  错误说明




#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "flowId":"123342342324", //认证流水号
    }
}

```

















