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
        "entCertStatus": 1 //企业认证状态
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
| flowId      | 是| string  |  上一步返回流水号|   |
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




#### 1.13 我的首页接口

##### 接口说明

我的首页信息接口



##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/my/index |

#####  输入参数





#####  错误说明




#####  返回实例
```json
{
    "c": 0,
    "m": null,
    "d": {
        "avatar": null, //头像
        "name": null, //昵称
        "mobile": "15201008961", //手机号
        "certStatus": 1, //认证状态
        "balance": 0 //合同余额
    }
}
```




#### 1.14 获取短信验证码

##### 接口说明

登录时，获取短信密码的功能，程序会有一个开关控制是否弹出动态页面验证码（防止短信接口被刷）

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/user/sendsms |
| token说明      |如果是更换手机号，校验手机身份需要登陆状态|

#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile      | 是| string  |  用户注册或登录时所填的手机号 |   |
| countryCode      | 否| string  | 注册或登录手机号码的国际区号| 客户端需要过滤掉非数字的字符，例如：+86处理成86，+1-90处理成190等。如果不传此值，则默认为中国区号86。 |
| deviceId      | 是| string  | 设备号| 只能是数字、大小写英文字母组成，且长度在1到100位之间  |
| smsType  | 否 | Integer  | 发短信的类型 | 验证码的下发类型 1或不填（赋默认值1）：短信验证码 2：语音验证码 |
| interfaceType   | 是 | Integer  | 发短信的接口类型 |1：注册登录接口的发短信 2：修改手机号的发短信，俩接口区别在于后者需要手机号不能存在  4:公众号手机号登录 5:用户手机发短信校验，确定用户身份（用于更换手机号） |
| captcha   | 否 | Integer  | 页面动态验证码 |用户获取短信验证码超过规定次数后弹出页面动态验证码。自测阶段恒需要弹动态验证码 |
| deviceType   | 否 | String  |设备类型 ||
| code   | 否 | string |参数签名 |原code算法：MD5(mobile + deviceId + VERSION_SECRET_KEY + ct)添加上国际区号后的code算法：MD5(countryCode + mobile + deviceId + VERSION_SECRET_KEY + ct)备注：生成code的countryCode和mobile都必须是过滤掉特殊字符的，否则生成的code与服务端的会匹配不上。|
| ct   | 否 | string |时间戳  |接口请求时的当前时间戳|
| loginVersion   | 是 | Integer | 当前支持登录的版本号  |目前支持loginVersion=1的版本登录 |

#####  错误说明

先整理可能的错误类型，具体对应的错误码实施时再确定：

1. 缺少必填的参数。

2. 无效的手机号码。

3. 手机号发送验证码次数超限。

4. 一分钟只能发送一条短信。

5. 用户操作异常。


#####  返回实例
```json
{
 
  "c": "0"
 
  "m": "操作成功",
 
  "d": {}
 
}
```



#### 1.14 实名认证修改说明

##### 接口说明

1. 原手机号认证获取短信验证码  /user/sendsms  interfaceType 5
2. 原手机号验证码认证 /user/mobile/update/step1
3. 新手机号验证码申请  /user/realname/update
4. 新手机号验证码认证  /user/mobile/update/step2



















