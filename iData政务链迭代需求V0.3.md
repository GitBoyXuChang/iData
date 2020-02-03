## iData政务链迭代需求V0.3

### 1、项目成员接口：

描述：项目管理表(SYSTEM_PROJECT_USER)



#### 1.1 批量添加项目成员

- 接口描述

  在已有的项目下添加项目的成员，可以进行批量操作

添加项目

- 接口入参

  请求头：

  Content-Type ：application/json

| 字段名称        | 字段类型 | 是否必填 | 备注                                                        |
| --------------- | -------- | -------- | ----------------------------------------------------------- |
| **projectId**   | String   | 是       | 项目名称                                                    |
| **projectName** | String   | 否       | 项目名称                                                    |
| **userId**      | String   | 是       | 成员用户的id                                                |
| **projectRole** | String   | 是       | 项目角色 所有者all，管理员admin,操作者operator,查看者viewer |

```json
[
	{
		"projectId":"618035918208512000",
		"projectName":"项目名称",
		"userId":"61125684580964352",
		"projectRole":"admin"
	},
	{
		"projectId":"618035918208512000",
		"projectName":"项目名称",
		"userId":"61125684580964350",
		"projectRole":"admin"
	}
]
```



- 接口请求路径

路径：/system/project/user/add

- 接口请求类型

类型：POST

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |



- 接口返回JSON

```json
{
    "returnCode": "System123",
    "returnMsg": "用户已存在项目",
    "nonceStr": "7cb3a1abf1854cff81eab02690e01808",
    "success": false,
    "data": null
}
```

#### 1.2 批量修改项目成员

- 接口描述

  在已有的项目下修改项目的成员，可以进行批量操作，只是修改该角色

添加项目

- 接口入参

  请求头：

  Content-Type ：application/json

| 字段名称        | 字段类型 | 是否必填 | 备注                                              |
| --------------- | -------- | -------- | ------------------------------------------------- |
| **id**          | String   | 是       | 项目成员表的id                                    |
| **projectRole** | String   | 是       | 项目角色，管理员admin,操作者operator,查看者viewer |

```json
[
	{
		"id":"659744278423805952",
		"projectRole":"viewer"
	},
	{
		"id":"659744278428000256",
		"projectRole":"admin"
	}
]
```



- 接口请求路径

路径：/system/project/user/edit

- 接口请求类型

类型：POST

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |



- 接口返回JSON

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "81a30eb0232a4d40a98d1246e2be7b97",
    "success": true,
    "data": true
}
```

#### 1.3分页条件查询项目成员

- 接口描述

  根据条件查询项目成员，条件为空表示不作为选择条件

- 接口入参

  请求头：

  Content-Type ：application/json

| 字段名称        | 字段类型 | 是否必填 | 备注                                              |
| --------------- | -------- | -------- | ------------------------------------------------- |
| **id**          | String   | 否       | 项目成员id                                        |
| **projectId**   | String   | 否       | 项目名称                                          |
| **projectName** | String   | 否       | 项目名称                                          |
| **userId**      | String   | 否       | 成员用户的id                                      |
| **projectRole** | String   | 否       | 项目角色，管理员admin,操作者operator,查看者viewer |
| pageNum         | Integer  | 是       |                                                   |
| pageSize        | Integer  | 是       |                                                   |

```json
http://127.0.0.1:8110/project/user/page?id&projectId&projectName&userId&projectRole&pageNum=1&pageSize=10
```



- 接口请求路径

路径：/system/project/user/page

- 接口请求类型

类型：GET

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |



- 接口返回JSON

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "a7d0edced62d427e907efbac7fe0e093",
    "success": true,
    "data": {
        "total": 2,
        "pageCount": 1,
        "pageNum": 1,
        "pageSize": 10,
        "datas": [
            {
                "id": "659744278423805952",
                "projectId": "618035918208512000",
                "projectName": "QA",
                "userId": "611256845809643520",
                "projectRole": "viewer"
            },
            {
                "id": "659744278428000256",
                "projectId": "618035918208512000",
                "projectName": "QA",
                "userId": "61125684580964350",
                "projectRole": "admin"
            }
        ]
    }
}
```

#### 1.4条件查询项目成员

- 接口描述

  根据条件查询项目成员，条件为空表示不作为选择条件

- 接口入参

  请求头：

  Content-Type ：application/json

| 字段名称        | 字段类型 | 是否必填 | 备注                                              |
| --------------- | -------- | -------- | ------------------------------------------------- |
| **id**          | String   | 否       | 项目成员id                                        |
| **projectId**   | String   | 否       | 项目名称                                          |
| **projectName** | String   | 否       | 项目名称                                          |
| **userId**      | String   | 否       | 成员用户的id                                      |
| **projectRole** | String   | 否       | 项目角色，管理员admin,操作者operator,查看者viewer |

```json
http://127.0.0.1:8110/project/user/query?id&projectId&projectName&userId&projectRole
```



- 接口请求路径

路径：/system/project/user/query

- 接口请求类型

类型：GET

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |



- 接口返回JSON

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "319d7761063c4314845f5d19a0578e5c",
    "success": true,
    "data": [
        {
            "id": "659744278423805952",
            "projectId": "618035918208512000",
            "projectName": "QA",
            "userId": "611256845809643520",
            "projectRole": "viewer"
        },
        {
            "id": "659744278428000256",
            "projectId": "618035918208512000",
            "projectName": "QA",
            "userId": "61125684580964350",
            "projectRole": "admin"
        }
    ]
}
```

#### 1.5批量删除项目成员

- 接口描述

  根据id删除项目成员

- 接口入参

  请求头：

  Content-Type ：application/json

| 字段名称 | 字段类型 | 是否必填 | 备注       |
| -------- | -------- | -------- | ---------- |
| **id**   | String   | 否       | 项目成员id |

```json
{
	"ids":["659466495298605056"]
}
```



- 接口请求路径

路径：/system/project/user/delete

- 接口请求类型

类型：DELETE

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |



- 接口返回JSON

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "81a30eb0232a4d40a98d1246e2be7b97",
    "success": true,
    "data": true
}
```

#### 

```json
INSERT INTO `idata`.`uaa_interface`(`interface_id`, `uri`, `method`, `module`, `name`, `remark`, `need_auth`, `support_auth_type`, `uri_type`) VALUES (196, '/system/project/user/add', 'POST', 'system', '批量添加项目成员', '批量添加项目成员', 1, 'token', '0');
INSERT INTO `idata`.`uaa_interface`(`interface_id`, `uri`, `method`, `module`, `name`, `remark`, `need_auth`, `support_auth_type`, `uri_type`) VALUES (197, '/system/project/user/edit', 'POST', 'system', '批量修改项目成员', '批量修改项目成员', 1, 'token', '0');
INSERT INTO `idata`.`uaa_interface`(`interface_id`, `uri`, `method`, `module`, `name`, `remark`, `need_auth`, `support_auth_type`, `uri_type`) VALUES (198, '/system/project/user/page', 'GET', 'system', '分页条件查询项目成员', '分页条件查询项目成员', 1, 'token', '0');
INSERT INTO `idata`.`uaa_interface`(`interface_id`, `uri`, `method`, `module`, `name`, `remark`, `need_auth`, `support_auth_type`, `uri_type`) VALUES (199, '/system/project/user/query', 'GET', 'system', '条件查询项目成员', '条件查询项目成员', 1, 'token', '0');
INSERT INTO `idata`.`uaa_interface`(`interface_id`, `uri`, `method`, `module`, `name`, `remark`, `need_auth`, `support_auth_type`, `uri_type`) VALUES (200, '/system/project/user/delete', 'POST', 'system', '批量删除项目成员', '批量删除项目成员', 1, 'token', '0');
```

