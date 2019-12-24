# 管理后台

[TOC]
## 修订记录
----

日期 | 作者 | 修订类型 | 修订内容 | 版本
---- | ---- | ---- | ---- | ---- |
2019年10月21日|冷立纲|A|新增设计方案|1.0

> 【修订类型：A-新增  M-修改 D-删除】

## 背景

蝙蝠租车，客户关系管理相关接口

## 产品说明


## 关键流程说明

## 接口说明


### 通用接口

-------




### 管理权限

-------


####  登录验证码接口

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/login_code |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile   | 是 | string  |  登陆手机号 |  |


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "smscode": "835898"  //测试环境返回验证码，线上发送短信验证码
    }
}


```

#####  错误实例


登录失败

```

{
    "c": 20023,
    "m": "一分钟只能发送一次短信",
    "d": null
}


```

####  登陆接口

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/login |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| mobile   | 是 | string  |  登陆手机号 |  |
| password   | 是 | string  |  登陆密码 |  |
| smscode   | 是 | string  |  短信验证码 |  |


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "menus": [     //菜单列表
            {
                "id": 3,   
                "title": "客户查询",  //菜单名
                "path": null,  //路径
                "parentId": 0, //父菜单，0 为顶级菜单
                "type": 0, //类型 0 普通 ，1 通配符
                "isMenu": 1, //是否菜单
                "createTime": 1571564520091, //创建时间
                "privilegePos": 0, //权限位
                "privilegeVal": 1,  //权限值
                "needAuth": 1, //是否需要权限认证
                "checked": false, //是否选中
                "subMenus": [ //子菜单
                    {
                        "id": 5,
                        "title": "我的客户",
                        "path": "/customer/list",
                        "parentId": 3,
                        "type": 0,
                        "isMenu": 1,
                        "createTime": 1571564853727,
                        "privilegePos": 0,
                        "privilegeVal": 2,
                        "needAuth": 1,
                        "checked": false,
                        "subMenus": null
                    },
                    {
                        "id": 6,
                        "title": "我的客户审核",
                        "path": "/my/customer_audit",
                        "parentId": 3,
                        "type": 0,
                        "isMenu": 1,
                        "createTime": 1571564912633,
                        "privilegePos": 0,
                        "privilegeVal": 4,
                        "needAuth": 1,
                        "checked": false,
                        "subMenus": null
                    }
                ]
            },
            {
                "id": 7,
                "title": "客户管理",
                "path": null,
                "parentId": 0,
                "type": 0,
                "isMenu": 1,
                "createTime": 1571564946707,
                "privilegePos": 0,
                "privilegeVal": 8,
                "needAuth": 1,
                "checked": false,
                "subMenus": [
                    {
                        "id": 8,
                        "title": "客户审核",
                        "path": "/customer/audit",
                        "parentId": 7,
                        "type": 0,
                        "isMenu": 1,
                        "createTime": 1571565091170,
                        "privilegePos": 0,
                        "privilegeVal": 16,
                        "needAuth": 1,
                        "checked": false,
                        "subMenus": null
                    },
                    {
                        "id": 9,
                        "title": "客户信息",
                        "path": "/customer/info",
                        "parentId": 7,
                        "type": 0,
                        "isMenu": 1,
                        "createTime": 1571565154486,
                        "privilegePos": 0,
                        "privilegeVal": 32,
                        "needAuth": 1,
                        "checked": false,
                        "subMenus": null
                    }
                ]
            },
            {
                "id": 11,
                "title": "权限管理",
                "path": "/resources/list",
                "parentId": 0,
                "type": 0,
                "isMenu": 1,
                "createTime": 1571565206179,
                "privilegePos": 0,
                "privilegeVal": 64,
                "needAuth": 1,
                "checked": false,
                "subMenus": [
                    {
                        "id": 12,
                        "title": "账号管理",
                        "path": null,
                        "parentId": 11,
                        "type": 0,
                        "isMenu": 1,
                        "createTime": 1571565222127,
                        "privilegePos": 0,
                        "privilegeVal": 128,
                        "needAuth": 1,
                        "checked": false,
                        "subMenus": null
                    },
                    {
                        "id": 13,
                        "title": "资源管理",
                        "path": "/resources/list",
                        "parentId": 11,
                        "type": 0,
                        "isMenu": 1,
                        "createTime": 1571584000492,
                        "privilegePos": 0,
                        "privilegeVal": 256,
                        "needAuth": 1,
                        "checked": false,
                        "subMenus": null
                    }
                ]
            }
        ],
        "user": {   //用户信息
            "id": 1,
            "realName": "王瑾", //姓名
            "gender": 1, //性别 1 男  -1 女
            "cardId": null, //身份证号码
            "birthday": null, //生日
            "wxNum": null, //微信号
            "mobile": "13260280107", //手机号
            "store": null, //所属门店
            "contactName": null, //联系人姓名
            "contactMobile": null, //联系人手机号
            "relationship": null, //关系
            "idCardImg1": null, //身份证 正面
            "idCardImg2": null, //身份证 反面
            "password": "17bc7964243108d78e795d79ef493a35", //登陆密码 md5 加密 
            "belongTo": 1, //归属
            "status": 1, // 状态 1 正常 -1 禁止登陆
            "privilege": null, //权限值
            "type": 1, // 类型 1超级管理员  0 普通管理员
            "createTime": null, //创建时间
            "updateTime": null //更新时间
        }
    }
}

```


####  账号管理（列表）

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/admin/list |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| realName   | 否 | string  |  姓名 |  |
| belongTo   | 否 | int  |  归属 |  1 总部 0 销售 |


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
        "pageSize": 10,
        "totalCount": 2,
        "currentPage": 1,
        "unit": "条",
        "extInfo": null,
        "result": [
            {
                "id": 2,   //id
                "realName": "小刚", //姓名
                "gender": 1, //性别 1 男 -1 女  0未知
                "cardId": null, //身份证
                "birthday": null, //生日
                "wxNum": null, //微信号
                "mobile": "15201008961", //手机号
                "store": null, //门店
                "contactName": null, //紧急联系人
                "contactMobile": null, //紧急联系人手机
                "relationship": null, //关系
                "idCardImg1": null, //身份证 正面
                "idCardImg2": null, //身份证 反面
                "password": "17bc7964243108d78e795d79ef493a35", //密码md5
                "belongTo": null, //归属  1 总部 0 销售
                "status": 1, //状态 1 正常  -1 禁止登陆
                "privilege": [   //权限
                    15
                ],
                "type": 0,  //类型 0 普通 1超级管理员
                "createTime": 1571660333483, //创建时间 
                "updateTime": 1571660885517 //更新时间
            }
        ],
        "firstPage": true,
        "lastPage": true,
        "nextPage": 1,
        "previousPage": 1,
        "pageCount": 1,
        "startIndex": 0,
        "endIndex": 10
    }
}


```


####  账号员详情

##### 请求说明

| http 请求方式          |get             |
|:------------- |:---------------:|
| url      |/admin/get |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 是 | int  |  管理员Id |  |


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
                "id": 2,   //id
                "realName": "小刚", //姓名
                "gender": 1, //性别 1 男 -1 女  0未知
                "cardId": null, //身份证
                "birthday": null, //生日
                "wxNum": null, //微信号
                "mobile": "15201008961", //手机号
                "store": null, //门店
                "contactName": null, //紧急联系人
                "contactMobile": null, //紧急联系人手机
                "relationship": null, //关系
                "idCardImg1": null, //身份证 正面
                "idCardImg2": null, //身份证 反面
                "password": "17bc7964243108d78e795d79ef493a35", //密码md5
                "belongTo": null, //归属  1 总部 0 销售
                "status": 1, //状态 1 正常  -1 禁止登陆
                "privilege": [   //权限
                    15
                ],
                "type": 0,  //类型 0 普通 1超级管理员
                "createTime": 1571660333483, //创建时间 
                "updateTime": 1571660885517 //更新时间
     }
}


```


####  添加管理员

##### 请求说明

| http 请求方式          |post             |
|:------------- |:---------------:|
| url      |/admin/add |


#####  输入参数

| 参数          |必选             | 类型       | 参数说明        | 备注          |
|:-------------|:---------------:|:-------------|:-------------|:-------------|
| id   | 否 | int  |  管理员Id |   有更新否则添加 |
| realName   | 是 | int  |  姓名  |  真实姓名 |
| gender   | 是 | int  |  性别  |   -1 女  1 男 0 未知 |
| cardId   | 是 | string  |  身份证号码  ||
| wxNum   | 是 | string  |  微信号 ||
| mobile   | 是 | string  |  手机号 ||
| contactName   | 是 | string  |  联系人姓名 ||
| contactMobile   | 是 | string  |  联系人电话 ||
| relationship   | 是 | int  |  关系 | 前端可自定义 |
| idCardImg1   | 是 | string  |  身份证正面 | |
| idCardImg2   | 是 | string  |  身份证反面 | |
| password   | 是 | string  |  密码 | |
| belongTo   | 是 | int  |  归属 | 1 总部 0 销售 |
| status   | 是 | int  |  状态 | 1  正常 -1 禁止登陆 |
| resources   | 是 | int[]  |  权限列表 | 权限值 |

	


#####  返回实例

```

{
    "c": 0,
    "m": null,
    "d": {
              
     }
}


```





























































































