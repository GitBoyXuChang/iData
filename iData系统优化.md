# iData系统优化

## 目录

[TOC]

> iData接口对接的POSTMAN
>
> iData.postman_collection.json



### 1、项目管理接口优化：

描述：项目管理表(SYSTEM_PROJECT)，添加IP_ADDRESS字段；

新增项目，修改项目的接口增加ipAddress字段；

#### 1.1 添加项目

- 接口描述

  表添加userId字段，存储的是请求头的userId 项目查询接口增加userId字段

添加项目

- 接口入参

  请求头：

  Content-Type ：application/json

  x-userid：613463581383565312（用户id）

| 字段名称           | 字段类型 | 是否必填 | 备注       |
| ------------------ | -------- | -------- | ---------- |
| **name**           | String   | 是       | 项目名称   |
| **contactPhone**   | String   | 是       | 联系人号码 |
| **host**           | String   | 是       | 节点地址   |
| **contact**        | String   | 是       | 联系人     |
| **organizationId** | String   | 是       | 部门id     |
| **description**    | String   | 是       | 描述       |
| **ipAddress**      | String   | 是       | Ip地址     |

- 接口请求路径

路径：/system/project/insert

- 接口请求类型

类型：POST

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |



- 接口返回JSON

```json
{
    id: "673743044357292032"
    number: "673743044357292032"
    name: "张水寿"
    description: "张水寿"
    organizationId: "619227683267555328"
    contact: "张水寿"
    contactPhone: "15678764937"
    host: "http://192.168.0.190"
    createTime: "2020-02-02T20:14:19.315+0000"
    sum: 24
    ipAddress: "192.168.0.190"
    userId: "668418773879775232"
    state: "2"
}
```

#### 1.2 修改项目

- 接口描述：

根据传入的id修改项目

- 接口入参

| 字段名称           | 字段类型 | 是否必填 | 备注       |
| ------------------ | -------- | -------- | ---------- |
| **id**             | String   | 是       | 项目id     |
| **contactPhone**   | String   | 否       | 联系人号码 |
| **host**           | String   | 否       | 节点地址   |
| **contact**        | String   | 否       | 联系人     |
| **organizationId** | String   | 否       | 部门id     |
| **description**    | String   | 否       | 描述       |
| **name**           | String   | 否       | 项目名称   |
| **ipAddress**      | String   | 是       | Ip地址     |

 

- 接口请求路径

路径：/system/project/update

- 接口请求类型

类型：POST

- 接口返回参数

| 字段名称 | 字段类型 | 是否必填 | 备注             |
| -------- | -------- | -------- | ---------------- |
| **data** | Boolean  | 是       | 返回操作是否成功 |

 

- 接口返回JSON



#### 1.3 查询项目

接口描述：

根据项目id查询项目

**l** **接口入参**

| 字段名称 | 字段类型 | 是否必填 | 备注 |
| -------- | -------- | -------- | ---- |
| **id**   | String   | 是       | id   |

 

**l** **接口请求路径**

路径：/system/project/get

**l** **接口请求类型**

类型：POST

**l** **接口返回参数**

| 字段名称           | 字段类型 | 是否必填 | 备注       |
| ------------------ | -------- | -------- | ---------- |
| **id**             | String   | 是       | 项目id     |
| **number**         | String   | 是       | 项目编号   |
| **name**           | String   | 是       | 项目名称   |
| **description**    | String   | 是       | 项目描述   |
| **organizationId** | String   | 是       | 部门ID     |
| **contact**        | String   | 是       | 联系人     |
| **contactPhone**   | String   | 是       | 联系人电话 |
| **host**           | String   | 是       | 节点地址   |
| **sum**            | String   | 是       | 总数       |
| **ipAddress**      | String   | 是       | Ip地址     |

 

**l** **接口返回JSON**





#### 1.4 分页条件查询

**l** **接口**描述：

根据入参条件查询项目

表添加userId字段，存储的是请求头的userId 项目查询接口增加userId字段

**l** **接口入参**

请求头：

Content-Type ：application/json

x-userid：613463581383565312（用户id）

| 字段名称           | 字段类型 | 是否必填 | 备注     |
| ------------------ | -------- | -------- | -------- |
| **name**           | String   | 否       | 项目名称 |
| **organizationId** | String   | 否       | 部门ID   |
| **pageSize**       | Integer  | 是       | 分页参数 |
| **pageNum**        | Integer  | 是       | 分页参数 |

 ```json
{
    "name":"7",
    "organizationId":"618494327940722688",
    "contact":"联系人",
    "contactPhone":"13800138000",
    "pageNum":1,
    "pageSize":10
}
 ```



**l** **接口请求路径**

路径：/system/project/page

**l** **接口请求类型**

类型：POST

**l** **接口返回参数**

| 字段名称       | 字段类型 | 是否必填 | 备注       |
| -------------- | -------- | -------- | ---------- |
| **returnCode** | String   | 是       | 成功为0000 |
| **returnMsg**  | String   | 是       | 返回信息   |
| **nonceStr**   | String   | 是       | 返回字符   |
| **success**    | Boolean  | 是       | 返回状态   |
| **data**       | 对象     | 是       | 返回数据   |

 

| data对象           | 字段类型 | 是否必填 | 备注       |
| ------------------ | -------- | -------- | ---------- |
| **id**             | String   | 是       | 项目id     |
| **number**         | String   | 是       | 项目编号   |
| **name**           | String   | 是       | 项目名称   |
| **description**    | String   | 是       | 项目描述   |
| **organizationId** | String   | 是       | 部门ID     |
| **contact**        | String   | 是       | 联系人     |
| **contactPhone**   | String   | 是       | 联系人电话 |
| **host**           | String   | 是       | 节点地址   |
| **sum**            | String   | 是       | 总数       |
| **ipAddress**      | String   | 是       | Ip地址     |

 

**l** **接口返回JSON**



 

### 2、吞吐量接口优化：

- 接口描述：

/blockinfo/throughput

吞吐量的时间区间由前端传入，后端进行计算；

根据区块信息和交易信息接口合成一个，先查询区块信息，有数据就返回，没有数据再查询交易信息。

- 接口路径

  /blockinfo/throughput

- 接口类型

  POST

- 接口入参

  | 字段名称  | 字段类型 | 是否必填 | 备注                    |
  | --------- | -------- | -------- | ----------------------- |
  | startTime | String   | 是       | 开始时间 yyyyMMddHHmmss |
  | endTime   | String   | 是       | 结束时间 yyyyMMddHHmmss |
  |           |          |          |                         |

  

- 接口返回

- 接口返回json

  ```jso
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "87a99dc03fd84cf086a4ee317609992a",
      "success": true,
      "data": 0.0
  }
  ```

  

### 3、区块交易分页查询

- 接口描述

  增加contractReqParam字段，对 CONTACT_REQ_PARAM字段进行模糊查询，

  增加blockHeight字段，对区块高度下的交易数据进行查询

- 接口路径

   /monitor/blockTransaction/page

- 接口入参

  | 字段名称         | 字段类型 | 是否必填 | 备注 |
  | ---------------- | -------- | -------- | ---- |
  | pageNum          | int      | 是       |      |
  | pageSize         | int      | 是       |      |
  | projectId        | String   |          |      |
  | txId             | String   |          |      |
  | contractReqParam | String   |          |      |

  

- 接口类型

  GET

- 接口返回

 ```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "c8d0c2870dd54fc397dd5838dcd257a9",
    "success": true,
    "data": {
        "total": 1,
        "pageCount": 1,
        "pageNum": 1,
        "pageSize": 10,
        "datas": [
            {
                "id": "626857056087175168",
                "txId": "5a1ec6c04f9af71c174d8e0f24671a31b9a89a5047c63807028b5ed824c28892",
                "peerNode": "peer0.org1.example.com",
                "transactionTime": "2019-09-26 19:06:08",
                "projectName": "QATB",
                "contractName": "material",
                "contractReqParam": "yangzejie2,md5",
                "blockHeight": 60,
                "contractFcn": "isExistMaterial",
                "outBlockName": null,
                "blockHash": null,
                "projectId": "619230915440160768",
                "organizationName": "QATB"
            }
        ]
    }
}
 ```



### 4、模板管理

#### 4.1 添加

- 接口描述

  模板表增加字段；

  添加模板接口：增加abbreviation中文字段

  添加模板接口：存储请求头userId

  查询模板只展示系统模板和当前项目所属的模板（根据请求头userId）

- 接口路径

  /system/template/insert

- 接口入参

  请求头：

  Content-Type ：application/json

  x-userid：613463581383565312（用户id）

  ```json
  {
    "name": "templatTestAbcsnewb",
    "description": "template1 desc",
    "fileBase64": "LyoKQ29weXJpZ2h0IElCTSBDb3JwLiAyMDE2IEFsbCBSaWdodHMgUmVzZXJ2ZWQuCgpMaWNlbnNlZCB1bmRlciB0aGUgQXBhY2hlIExpY2Vuc2UsIFZlcnNpb24gMi4wICh0aGUgIkxpY2Vuc2UiKTsKeW91IG1heSBub3QgdXNlIHRoaXMgZmlsZSBleGNlcHQgaW4gY29tcGxpYW5jZSB3aXRoIHRoZSBMaWNlbnNlLgpZb3UgbWF5IG9idGFpbiBhIGNvcHkgb2YgdGhlIExpY2Vuc2UgYXQKCgkJIGh0dHA6Ly93d3cuYXBhY2hlLm9yZy9saWNlbnNlcy9MSUNFTlNFLTIuMAoKVW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzb2Z0d2FyZQpkaXN0cmlidXRlZCB1bmRlciB0aGUgTGljZW5zZSBpcyBkaXN0cmlidXRlZCBvbiBhbiAiQVMgSVMiIEJBU0lTLApXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IgaW1wbGllZC4KU2VlIHRoZSBMaWNlbnNlIGZvciB0aGUgc3BlY2lmaWMgbGFuZ3VhZ2UgZ292ZXJuaW5nIHBlcm1pc3Npb25zIGFuZApsaW1pdGF0aW9ucyB1bmRlciB0aGUgTGljZW5zZS4KKi8KCnBhY2thZ2UgbWFpbgoKLy9XQVJOSU5HIC0gdGhpcyBjaGFpbmNvZGUncyBJRCBpcyBoYXJkLWNvZGVkIGluIGNoYWluY29kZV9leGFtcGxlMDQgdG8gaWxsdXN0cmF0ZSBvbmUgd2F5IG9mCi8vY2FsbGluZyBjaGFpbmNvZGUgZnJvbSBhIGNoYWluY29kZS4gSWYgdGhpcyBleGFtcGxlIGlzIG1vZGlmaWVkLCBjaGFpbmNvZGVfZXhhbXBsZTA0LmdvIGhhcwovL3RvIGJlIG1vZGlmaWVkIGFzIHdlbGwgd2l0aCB0aGUgbmV3IElEIG9mIGNoYWluY29kZV9leGFtcGxlMDIuCi8vY2hhaW5jb2RlX2V4YW1wbGUwNSBzaG93J3MgaG93IGNoYWluY29kZSBJRCBjYW4gYmUgcGFzc2VkIGluIGFzIGEgcGFyYW1ldGVyIGluc3RlYWQgb2YKLy9oYXJkLWNvZGluZy4KCmltcG9ydCAoCgkiZm10IgoJInN0cmNvbnYiCgoJImdpdGh1Yi5jb20vaHlwZXJsZWRnZXIvZmFicmljL2NvcmUvY2hhaW5jb2RlL3NoaW0iCglwYiAiZ2l0aHViLmNvbS9oeXBlcmxlZGdlci9mYWJyaWMvcHJvdG9zL3BlZXIiCikKCi8vIFNpbXBsZUNoYWluY29kZSBleGFtcGxlIHNpbXBsZSBDaGFpbmNvZGUgaW1wbGVtZW50YXRpb24KdHlwZSBTaW1wbGVDaGFpbmNvZGUgc3RydWN0IHsKfQoKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBJbml0KHN0dWIgc2hpbS5DaGFpbmNvZGVTdHViSW50ZXJmYWNlKSBwYi5SZXNwb25zZSB7CglmbXQuUHJpbnRsbigiZXgwMiBJbml0IikKCV8sIGFyZ3MgOj0gc3R1Yi5HZXRGdW5jdGlvbkFuZFBhcmFtZXRlcnMoKQoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBlcnIgZXJyb3IKCglpZiBsZW4oYXJncykgIT0gNCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkluY29ycmVjdCBudW1iZXIgb2YgYXJndW1lbnRzLiBFeHBlY3RpbmcgNCIpCgl9CgoJLy8gSW5pdGlhbGl6ZSB0aGUgY2hhaW5jb2RlCglBID0gYXJnc1swXQoJQXZhbCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMV0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRXhwZWN0aW5nIGludGVnZXIgdmFsdWUgZm9yIGFzc2V0IGhvbGRpbmciKQoJfQoJQiA9IGFyZ3NbMl0KCUJ2YWwsIGVyciA9IHN0cmNvbnYuQXRvaShhcmdzWzNdKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkV4cGVjdGluZyBpbnRlZ2VyIHZhbHVlIGZvciBhc3NldCBob2xkaW5nIikKCX0KCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSB0byB0aGUgbGVkZ2VyCgllcnIgPSBzdHViLlB1dFN0YXRlKEEsIFtdYnl0ZShzdHJjb252Lkl0b2EoQXZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJZXJyID0gc3R1Yi5QdXRTdGF0ZShCLCBbXWJ5dGUoc3RyY29udi5JdG9hKEJ2YWwpKSkKCWlmIGVyciAhPSBuaWwgewoJCXJldHVybiBzaGltLkVycm9yKGVyci5FcnJvcigpKQoJfQoKCXJldHVybiBzaGltLlN1Y2Nlc3MobmlsKQp9CgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIEludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSkgcGIuUmVzcG9uc2UgewoJZm10LlByaW50bG4oImV4MDIgSW52b2tlIikKCWZ1bmN0aW9uLCBhcmdzIDo9IHN0dWIuR2V0RnVuY3Rpb25BbmRQYXJhbWV0ZXJzKCkKCWlmIGZ1bmN0aW9uID09ICJpbnZva2UiIHsKCQkvLyBNYWtlIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgoJCXJldHVybiB0Lmludm9rZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJkZWxldGUiIHsKCQkvLyBEZWxldGVzIGFuIGVudGl0eSBmcm9tIGl0cyBzdGF0ZQoJCXJldHVybiB0LmRlbGV0ZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJxdWVyeSIgewoJCS8vIHRoZSBvbGQgIlF1ZXJ5IiBpcyBub3cgaW1wbGVtdG5lZCBpbiBpbnZva2UKCQlyZXR1cm4gdC5xdWVyeShzdHViLCBhcmdzKQoJfQoKCXJldHVybiBzaGltLkVycm9yKCJJbnZhbGlkIGludm9rZSBmdW5jdGlvbiBuYW1lLiBFeHBlY3RpbmcgXCJpbnZva2VcIiBcImRlbGV0ZVwiIFwicXVlcnlcIiIpCn0KCi8vIFRyYW5zYWN0aW9uIG1ha2VzIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIGludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBYIGludCAgICAgICAgICAvLyBUcmFuc2FjdGlvbiB2YWx1ZQoJdmFyIGVyciBlcnJvcgoKCWlmIGxlbihhcmdzKSAhPSAzIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAzIikKCX0KCglBID0gYXJnc1swXQoJQiA9IGFyZ3NbMV0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJLy8gVE9ETzogd2lsbCBiZSBuaWNlIHRvIGhhdmUgYSBHZXRBbGxTdGF0ZSBjYWxsIHRvIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkZhaWxlZCB0byBnZXQgc3RhdGUiKQoJfQoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkVudGl0eSBub3QgZm91bmQiKQoJfQoJQXZhbCwgXyA9IHN0cmNvbnYuQXRvaShzdHJpbmcoQXZhbGJ5dGVzKSkKCglCdmFsYnl0ZXMsIGVyciA6PSBzdHViLkdldFN0YXRlKEIpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGdldCBzdGF0ZSIpCgl9CglpZiBCdmFsYnl0ZXMgPT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRW50aXR5IG5vdCBmb3VuZCIpCgl9CglCdmFsLCBfID0gc3RyY29udi5BdG9pKHN0cmluZyhCdmFsYnl0ZXMpKQoKCS8vIFBlcmZvcm0gdGhlIGV4ZWN1dGlvbgoJWCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMl0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW52YWxpZCB0cmFuc2FjdGlvbiBhbW91bnQsIGV4cGVjdGluZyBhIGludGVnZXIgdmFsdWUiKQoJfQoJQXZhbCA9IEF2YWwgLSBYCglCdmFsID0gQnZhbCArIFgKCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSBiYWNrIHRvIHRoZSBsZWRnZXIKCWVyciA9IHN0dWIuUHV0U3RhdGUoQSwgW11ieXRlKHN0cmNvbnYuSXRvYShBdmFsKSkpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcihlcnIuRXJyb3IoKSkKCX0KCgllcnIgPSBzdHViLlB1dFN0YXRlKEIsIFtdYnl0ZShzdHJjb252Lkl0b2EoQnZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIERlbGV0ZXMgYW4gZW50aXR5IGZyb20gc3RhdGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBkZWxldGUoc3R1YiBzaGltLkNoYWluY29kZVN0dWJJbnRlcmZhY2UsIGFyZ3MgW11zdHJpbmcpIHBiLlJlc3BvbnNlIHsKCWlmIGxlbihhcmdzKSAhPSAxIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAxIikKCX0KCglBIDo9IGFyZ3NbMF0KCgkvLyBEZWxldGUgdGhlIGtleSBmcm9tIHRoZSBzdGF0ZSBpbiBsZWRnZXIKCWVyciA6PSBzdHViLkRlbFN0YXRlKEEpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGRlbGV0ZSBzdGF0ZSIpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIHF1ZXJ5IGNhbGxiYWNrIHJlcHJlc2VudGluZyB0aGUgcXVlcnkgb2YgYSBjaGFpbmNvZGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBxdWVyeShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEgc3RyaW5nIC8vIEVudGl0aWVzCgl2YXIgZXJyIGVycm9yCgoJaWYgbGVuKGFyZ3MpICE9IDEgewoJCXJldHVybiBzaGltLkVycm9yKCJJbmNvcnJlY3QgbnVtYmVyIG9mIGFyZ3VtZW50cy4gRXhwZWN0aW5nIG5hbWUgb2YgdGhlIHBlcnNvbiB0byBxdWVyeSIpCgl9CgoJQSA9IGFyZ3NbMF0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJGYWlsZWQgdG8gZ2V0IHN0YXRlIGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJOaWwgYW1vdW50IGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJanNvblJlc3AgOj0gIntcIk5hbWVcIjpcIiIgKyBBICsgIlwiLFwiQW1vdW50XCI6XCIiICsgc3RyaW5nKEF2YWxieXRlcykgKyAiXCJ9IgoJZm10LlByaW50ZigiUXVlcnkgUmVzcG9uc2U6JXNcbiIsIGpzb25SZXNwKQoJcmV0dXJuIHNoaW0uU3VjY2VzcyhBdmFsYnl0ZXMpCn0KCmZ1bmMgbWFpbigpIHsKCWVyciA6PSBzaGltLlN0YXJ0KG5ldyhTaW1wbGVDaGFpbmNvZGUpKQoJaWYgZXJyICE9IG5pbCB7CgkJZm10LlByaW50ZigiRXJyb3Igc3RhcnRpbmcgU2ltcGxlIGNoYWluY29kZTogJXMiLCBlcnIpCgl9Cn0K",
  	"type":"user",
  	"abbreviation":"中文名"
  }
  ```

  

- 接口返回

  ```json
  
  ```

  

#### 4.2 分页条件查询

- 接口描述

  模板表增加字段；

  添加模板接口：增加abbreviation中文字段

  添加模板接口：存储请求头userId

  查询模板只展示系统模板和当前项目所属的模板（根据请求头userId）

- 接口路径

  /system/template/page

- 接口入参

  请求头：

  Content-Type ：application/json

  x-userid：613463581383565312（用户id）

  ```json
  {
  	"number":"",
  	"name":"",
  	"pageNum":1,
  	"pageSize":10
  }
  ```

  

- 接口返回

 ```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "f9be6679798f487f9acc7ec502f17116",
    "success": true,
    "data": {
        "total": 6,
        "pageCount": 1,
        "pageNum": 1,
        "pageSize": 10,
        "datas": [
            {
                "id": "632151920815312896",
                "number": "632151920815312896",
                "createTime": "2019/10/11",
                "state": "0",
                "name": "templatTestAbcsnewb",
                "description": "testC desc",
                "fileBase64": null,
                "type": "user",
                "abbreviation": "别名",
                "userId": "613463581383565312"
            },
            {
                "id": "627152419612393472",
                "number": "627152419612393472",
                "createTime": "2019/09/27",
                "state": "0",
                "name": "templatTestAbcsnew",
                "description": "template1 desc",
                "fileBase64": null,
                "type": "user",
                "abbreviation": "别名",
                "userId": "613463581383565312"
            },
            {
                "id": "624999692530692096",
                "number": "624999692530692096",
                "createTime": "2019/09/21",
                "state": "0",
                "name": "import",
                "description": "import ",
                "fileBase64": null,
                "type": "user",
                "abbreviation": "别名",
                "userId": "613463581383565312"
            },
            {
                "id": "619232381265522688",
                "number": "619232381265522688",
                "createTime": "2019/09/05",
                "state": "0",
                "name": "Testf",
                "description": "TEST",
                "fileBase64": null,
                "type": "user",
                "abbreviation": "别名",
                "userId": "613463581383565312"
            },
            {
                "id": "619231373659484160",
                "number": "619231373659484160",
                "createTime": "2019/09/05",
                "state": "0",
                "name": "TEST",
                "description": "TEST",
                "fileBase64": null,
                "type": "user",
                "abbreviation": "别名",
                "userId": "613463581383565312"
            },
            {
                "id": "618167713155526656",
                "number": "618167713155526656",
                "createTime": "2019/09/02",
                "state": "0",
                "name": "testC",
                "description": "testC desc",
                "fileBase64": null,
                "type": "user",
                "abbreviation": "别名",
                "userId": "613463581383565312"
            }
        ]
    }
}
 ```

#### 4.3 修改

- 接口描述：

  修改

- 接口入参：

  请求头：

  Content-Type ：application/json

  x-userid：613463581383565312（用户id）

  ```json
  {
    "name": "templatTestAbcsnewb",
    "id":"632151920815312896",
    "description": "testC desc",
    "fileBase64": "LyoKQ29weXJpZ2h0IElCTSBDb3JwLiAyMDE2IEFsbCBSaWdodHMgUmVzZXJ2ZWQuCgpMaWNlbnNlZCB1bmRlciB0aGUgQXBhY2hlIExpY2Vuc2UsIFZlcnNpb24gMi4wICh0aGUgIkxpY2Vuc2UiKTsKeW91IG1heSBub3QgdXNlIHRoaXMgZmlsZSBleGNlcHQgaW4gY29tcGxpYW5jZSB3aXRoIHRoZSBMaWNlbnNlLgpZb3UgbWF5IG9idGFpbiBhIGNvcHkgb2YgdGhlIExpY2Vuc2UgYXQKCgkJIGh0dHA6Ly93d3cuYXBhY2hlLm9yZy9saWNlbnNlcy9MSUNFTlNFLTIuMAoKVW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzb2Z0d2FyZQpkaXN0cmlidXRlZCB1bmRlciB0aGUgTGljZW5zZSBpcyBkaXN0cmlidXRlZCBvbiBhbiAiQVMgSVMiIEJBU0lTLApXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IgaW1wbGllZC4KU2VlIHRoZSBMaWNlbnNlIGZvciB0aGUgc3BlY2lmaWMgbGFuZ3VhZ2UgZ292ZXJuaW5nIHBlcm1pc3Npb25zIGFuZApsaW1pdGF0aW9ucyB1bmRlciB0aGUgTGljZW5zZS4KKi8KCnBhY2thZ2UgbWFpbgoKLy9XQVJOSU5HIC0gdGhpcyBjaGFpbmNvZGUncyBJRCBpcyBoYXJkLWNvZGVkIGluIGNoYWluY29kZV9leGFtcGxlMDQgdG8gaWxsdXN0cmF0ZSBvbmUgd2F5IG9mCi8vY2FsbGluZyBjaGFpbmNvZGUgZnJvbSBhIGNoYWluY29kZS4gSWYgdGhpcyBleGFtcGxlIGlzIG1vZGlmaWVkLCBjaGFpbmNvZGVfZXhhbXBsZTA0LmdvIGhhcwovL3RvIGJlIG1vZGlmaWVkIGFzIHdlbGwgd2l0aCB0aGUgbmV3IElEIG9mIGNoYWluY29kZV9leGFtcGxlMDIuCi8vY2hhaW5jb2RlX2V4YW1wbGUwNSBzaG93J3MgaG93IGNoYWluY29kZSBJRCBjYW4gYmUgcGFzc2VkIGluIGFzIGEgcGFyYW1ldGVyIGluc3RlYWQgb2YKLy9oYXJkLWNvZGluZy4KCmltcG9ydCAoCgkiZm10IgoJInN0cmNvbnYiCgoJImdpdGh1Yi5jb20vaHlwZXJsZWRnZXIvZmFicmljL2NvcmUvY2hhaW5jb2RlL3NoaW0iCglwYiAiZ2l0aHViLmNvbS9oeXBlcmxlZGdlci9mYWJyaWMvcHJvdG9zL3BlZXIiCikKCi8vIFNpbXBsZUNoYWluY29kZSBleGFtcGxlIHNpbXBsZSBDaGFpbmNvZGUgaW1wbGVtZW50YXRpb24KdHlwZSBTaW1wbGVDaGFpbmNvZGUgc3RydWN0IHsKfQoKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBJbml0KHN0dWIgc2hpbS5DaGFpbmNvZGVTdHViSW50ZXJmYWNlKSBwYi5SZXNwb25zZSB7CglmbXQuUHJpbnRsbigiZXgwMiBJbml0IikKCV8sIGFyZ3MgOj0gc3R1Yi5HZXRGdW5jdGlvbkFuZFBhcmFtZXRlcnMoKQoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBlcnIgZXJyb3IKCglpZiBsZW4oYXJncykgIT0gNCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkluY29ycmVjdCBudW1iZXIgb2YgYXJndW1lbnRzLiBFeHBlY3RpbmcgNCIpCgl9CgoJLy8gSW5pdGlhbGl6ZSB0aGUgY2hhaW5jb2RlCglBID0gYXJnc1swXQoJQXZhbCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMV0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRXhwZWN0aW5nIGludGVnZXIgdmFsdWUgZm9yIGFzc2V0IGhvbGRpbmciKQoJfQoJQiA9IGFyZ3NbMl0KCUJ2YWwsIGVyciA9IHN0cmNvbnYuQXRvaShhcmdzWzNdKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkV4cGVjdGluZyBpbnRlZ2VyIHZhbHVlIGZvciBhc3NldCBob2xkaW5nIikKCX0KCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSB0byB0aGUgbGVkZ2VyCgllcnIgPSBzdHViLlB1dFN0YXRlKEEsIFtdYnl0ZShzdHJjb252Lkl0b2EoQXZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJZXJyID0gc3R1Yi5QdXRTdGF0ZShCLCBbXWJ5dGUoc3RyY29udi5JdG9hKEJ2YWwpKSkKCWlmIGVyciAhPSBuaWwgewoJCXJldHVybiBzaGltLkVycm9yKGVyci5FcnJvcigpKQoJfQoKCXJldHVybiBzaGltLlN1Y2Nlc3MobmlsKQp9CgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIEludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSkgcGIuUmVzcG9uc2UgewoJZm10LlByaW50bG4oImV4MDIgSW52b2tlIikKCWZ1bmN0aW9uLCBhcmdzIDo9IHN0dWIuR2V0RnVuY3Rpb25BbmRQYXJhbWV0ZXJzKCkKCWlmIGZ1bmN0aW9uID09ICJpbnZva2UiIHsKCQkvLyBNYWtlIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgoJCXJldHVybiB0Lmludm9rZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJkZWxldGUiIHsKCQkvLyBEZWxldGVzIGFuIGVudGl0eSBmcm9tIGl0cyBzdGF0ZQoJCXJldHVybiB0LmRlbGV0ZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJxdWVyeSIgewoJCS8vIHRoZSBvbGQgIlF1ZXJ5IiBpcyBub3cgaW1wbGVtdG5lZCBpbiBpbnZva2UKCQlyZXR1cm4gdC5xdWVyeShzdHViLCBhcmdzKQoJfQoKCXJldHVybiBzaGltLkVycm9yKCJJbnZhbGlkIGludm9rZSBmdW5jdGlvbiBuYW1lLiBFeHBlY3RpbmcgXCJpbnZva2VcIiBcImRlbGV0ZVwiIFwicXVlcnlcIiIpCn0KCi8vIFRyYW5zYWN0aW9uIG1ha2VzIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIGludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBYIGludCAgICAgICAgICAvLyBUcmFuc2FjdGlvbiB2YWx1ZQoJdmFyIGVyciBlcnJvcgoKCWlmIGxlbihhcmdzKSAhPSAzIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAzIikKCX0KCglBID0gYXJnc1swXQoJQiA9IGFyZ3NbMV0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJLy8gVE9ETzogd2lsbCBiZSBuaWNlIHRvIGhhdmUgYSBHZXRBbGxTdGF0ZSBjYWxsIHRvIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkZhaWxlZCB0byBnZXQgc3RhdGUiKQoJfQoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkVudGl0eSBub3QgZm91bmQiKQoJfQoJQXZhbCwgXyA9IHN0cmNvbnYuQXRvaShzdHJpbmcoQXZhbGJ5dGVzKSkKCglCdmFsYnl0ZXMsIGVyciA6PSBzdHViLkdldFN0YXRlKEIpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGdldCBzdGF0ZSIpCgl9CglpZiBCdmFsYnl0ZXMgPT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRW50aXR5IG5vdCBmb3VuZCIpCgl9CglCdmFsLCBfID0gc3RyY29udi5BdG9pKHN0cmluZyhCdmFsYnl0ZXMpKQoKCS8vIFBlcmZvcm0gdGhlIGV4ZWN1dGlvbgoJWCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMl0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW52YWxpZCB0cmFuc2FjdGlvbiBhbW91bnQsIGV4cGVjdGluZyBhIGludGVnZXIgdmFsdWUiKQoJfQoJQXZhbCA9IEF2YWwgLSBYCglCdmFsID0gQnZhbCArIFgKCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSBiYWNrIHRvIHRoZSBsZWRnZXIKCWVyciA9IHN0dWIuUHV0U3RhdGUoQSwgW11ieXRlKHN0cmNvbnYuSXRvYShBdmFsKSkpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcihlcnIuRXJyb3IoKSkKCX0KCgllcnIgPSBzdHViLlB1dFN0YXRlKEIsIFtdYnl0ZShzdHJjb252Lkl0b2EoQnZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIERlbGV0ZXMgYW4gZW50aXR5IGZyb20gc3RhdGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBkZWxldGUoc3R1YiBzaGltLkNoYWluY29kZVN0dWJJbnRlcmZhY2UsIGFyZ3MgW11zdHJpbmcpIHBiLlJlc3BvbnNlIHsKCWlmIGxlbihhcmdzKSAhPSAxIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAxIikKCX0KCglBIDo9IGFyZ3NbMF0KCgkvLyBEZWxldGUgdGhlIGtleSBmcm9tIHRoZSBzdGF0ZSBpbiBsZWRnZXIKCWVyciA6PSBzdHViLkRlbFN0YXRlKEEpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGRlbGV0ZSBzdGF0ZSIpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIHF1ZXJ5IGNhbGxiYWNrIHJlcHJlc2VudGluZyB0aGUgcXVlcnkgb2YgYSBjaGFpbmNvZGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBxdWVyeShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEgc3RyaW5nIC8vIEVudGl0aWVzCgl2YXIgZXJyIGVycm9yCgoJaWYgbGVuKGFyZ3MpICE9IDEgewoJCXJldHVybiBzaGltLkVycm9yKCJJbmNvcnJlY3QgbnVtYmVyIG9mIGFyZ3VtZW50cy4gRXhwZWN0aW5nIG5hbWUgb2YgdGhlIHBlcnNvbiB0byBxdWVyeSIpCgl9CgoJQSA9IGFyZ3NbMF0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJGYWlsZWQgdG8gZ2V0IHN0YXRlIGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJOaWwgYW1vdW50IGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJanNvblJlc3AgOj0gIntcIk5hbWVcIjpcIiIgKyBBICsgIlwiLFwiQW1vdW50XCI6XCIiICsgc3RyaW5nKEF2YWxieXRlcykgKyAiXCJ9IgoJZm10LlByaW50ZigiUXVlcnkgUmVzcG9uc2U6JXNcbiIsIGpzb25SZXNwKQoJcmV0dXJuIHNoaW0uU3VjY2VzcyhBdmFsYnl0ZXMpCn0KCmZ1bmMgbWFpbigpIHsKCWVyciA6PSBzaGltLlN0YXJ0KG5ldyhTaW1wbGVDaGFpbmNvZGUpKQoJaWYgZXJyICE9IG5pbCB7CgkJZm10LlByaW50ZigiRXJyb3Igc3RhcnRpbmcgU2ltcGxlIGNoYWluY29kZTogJXMiLCBlcnIpCgl9Cn0K",
    "abbreviation":"别名"
  }
  ```

  

- 接口类型：

  POST

- 接口路径：

  /system/template/update

- 接口返回：

  ```json
  
  ```

  

### 5、合约管理

合约表新增字段；

添加合约接口：增加abbreviation中文字段

合约查询：根据请求头userId查找所属的项目，进行查询。

####  5.1 分页条件查询

- 接口描述

  分页条件查询

- 接口入参

  请求头：

  Content-Type ：application/json

  x-userid：613463581383565312（用户id）

  ```json
  {
  	"projectId":"",
  	"number":"",
  	"state":"",
  	"abbreviation":"",
  	"pageNum":1,
  	"pageSize":10
  }
  ```

  

- 接口路径

  /system/contract/query

- 接口类型

  POST

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "9bae8b67ed1e48c79989e27a939ac11b",
      "success": true,
      "data": {
          "total": 7,
          "pageCount": 1,
          "pageNum": 1,
          "pageSize": 10,
          "datas": [
              {
                  "id": "632173170451222528",
                  "number": "632173170451222529",
                  "projectId": "626080036625387520",
                  "createTime": "2019/10/11",
                  "state": "0",
                  "serverVersion": null,
                  "fileBase64": null,
                  "description": "contactTest desc",
                  "name": "contacttestaaa",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              },
              {
                  "id": "632172772374024192",
                  "number": "632172772374024193",
                  "projectId": "626080036625387520",
                  "createTime": "2019/10/11",
                  "state": "0",
                  "serverVersion": null,
                  "fileBase64": null,
                  "description": "contactTest desc",
                  "name": "contacttestaa",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              },
              {
                  "id": "632172066443300864",
                  "number": "632172066443300865",
                  "projectId": "626080036625387520",
                  "createTime": "2019/10/11",
                  "state": "0",
                  "serverVersion": null,
                  "fileBase64": null,
                  "description": "contactTest desc",
                  "name": "contacttesta",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              },
              {
                  "id": "619136508674191360",
                  "number": "619136508674191361",
                  "projectId": "619227683267555328",
                  "createTime": "2019/09/05",
                  "state": "0",
                  "serverVersion": "1.1",
                  "fileBase64": null,
                  "description": "QA",
                  "name": "QATB",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              },
              {
                  "id": "619227683267555328",
                  "number": "618171849074814977",
                  "projectId": "619227683267555328",
                  "createTime": "2019/08/01",
                  "state": "0",
                  "serverVersion": null,
                  "fileBase64": null,
                  "description": "QA",
                  "name": "QA",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              },
              {
                  "id": "619120810086379520",
                  "number": "619120810086379521",
                  "projectId": "619227683267555328",
                  "createTime": "2019/08/01",
                  "state": "0",
                  "serverVersion": "1.0",
                  "fileBase64": null,
                  "description": "QA",
                  "name": "property",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              },
              {
                  "id": "619227683267555311",
                  "number": "619117779663990785",
                  "projectId": "619227683267555328",
                  "createTime": "2019/08/01",
                  "state": "0",
                  "serverVersion": null,
                  "fileBase64": null,
                  "description": "QA",
                  "name": "QAT",
                  "abbreviation": "中文简称",
                  "userId": "613463581383565312"
              }
          ]
      }
  }
  ```

  

####  5.2 添加

- 接口描述

  添加

- 接口入参

  

  ```json
  {
  	"contractName":"contacttestab",
  	"projectId":"613322810009436160",
  	"contractDesc":"contactTest desc",
  	"fileBase64": "LyoKQ29weXJpZ2h0IElCTSBDb3JwLiAyMDE2IEFsbCBSaWdodHMgUmVzZXJ2ZWQuCgpMaWNlbnNlZCB1bmRlciB0aGUgQXBhY2hlIExpY2Vuc2UsIFZlcnNpb24gMi4wICh0aGUgIkxpY2Vuc2UiKTsKeW91IG1heSBub3QgdXNlIHRoaXMgZmlsZSBleGNlcHQgaW4gY29tcGxpYW5jZSB3aXRoIHRoZSBMaWNlbnNlLgpZb3UgbWF5IG9idGFpbiBhIGNvcHkgb2YgdGhlIExpY2Vuc2UgYXQKCgkJIGh0dHA6Ly93d3cuYXBhY2hlLm9yZy9saWNlbnNlcy9MSUNFTlNFLTIuMAoKVW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzb2Z0d2FyZQpkaXN0cmlidXRlZCB1bmRlciB0aGUgTGljZW5zZSBpcyBkaXN0cmlidXRlZCBvbiBhbiAiQVMgSVMiIEJBU0lTLApXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IgaW1wbGllZC4KU2VlIHRoZSBMaWNlbnNlIGZvciB0aGUgc3BlY2lmaWMgbGFuZ3VhZ2UgZ292ZXJuaW5nIHBlcm1pc3Npb25zIGFuZApsaW1pdGF0aW9ucyB1bmRlciB0aGUgTGljZW5zZS4KKi8KCnBhY2thZ2UgbWFpbgoKLy9XQVJOSU5HIC0gdGhpcyBjaGFpbmNvZGUncyBJRCBpcyBoYXJkLWNvZGVkIGluIGNoYWluY29kZV9leGFtcGxlMDQgdG8gaWxsdXN0cmF0ZSBvbmUgd2F5IG9mCi8vY2FsbGluZyBjaGFpbmNvZGUgZnJvbSBhIGNoYWluY29kZS4gSWYgdGhpcyBleGFtcGxlIGlzIG1vZGlmaWVkLCBjaGFpbmNvZGVfZXhhbXBsZTA0LmdvIGhhcwovL3RvIGJlIG1vZGlmaWVkIGFzIHdlbGwgd2l0aCB0aGUgbmV3IElEIG9mIGNoYWluY29kZV9leGFtcGxlMDIuCi8vY2hhaW5jb2RlX2V4YW1wbGUwNSBzaG93J3MgaG93IGNoYWluY29kZSBJRCBjYW4gYmUgcGFzc2VkIGluIGFzIGEgcGFyYW1ldGVyIGluc3RlYWQgb2YKLy9oYXJkLWNvZGluZy4KCmltcG9ydCAoCgkiZm10IgoJInN0cmNvbnYiCgoJImdpdGh1Yi5jb20vaHlwZXJsZWRnZXIvZmFicmljL2NvcmUvY2hhaW5jb2RlL3NoaW0iCglwYiAiZ2l0aHViLmNvbS9oeXBlcmxlZGdlci9mYWJyaWMvcHJvdG9zL3BlZXIiCikKCi8vIFNpbXBsZUNoYWluY29kZSBleGFtcGxlIHNpbXBsZSBDaGFpbmNvZGUgaW1wbGVtZW50YXRpb24KdHlwZSBTaW1wbGVDaGFpbmNvZGUgc3RydWN0IHsKfQoKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBJbml0KHN0dWIgc2hpbS5DaGFpbmNvZGVTdHViSW50ZXJmYWNlKSBwYi5SZXNwb25zZSB7CglmbXQuUHJpbnRsbigiZXgwMiBJbml0IikKCV8sIGFyZ3MgOj0gc3R1Yi5HZXRGdW5jdGlvbkFuZFBhcmFtZXRlcnMoKQoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBlcnIgZXJyb3IKCglpZiBsZW4oYXJncykgIT0gNCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkluY29ycmVjdCBudW1iZXIgb2YgYXJndW1lbnRzLiBFeHBlY3RpbmcgNCIpCgl9CgoJLy8gSW5pdGlhbGl6ZSB0aGUgY2hhaW5jb2RlCglBID0gYXJnc1swXQoJQXZhbCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMV0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRXhwZWN0aW5nIGludGVnZXIgdmFsdWUgZm9yIGFzc2V0IGhvbGRpbmciKQoJfQoJQiA9IGFyZ3NbMl0KCUJ2YWwsIGVyciA9IHN0cmNvbnYuQXRvaShhcmdzWzNdKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkV4cGVjdGluZyBpbnRlZ2VyIHZhbHVlIGZvciBhc3NldCBob2xkaW5nIikKCX0KCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSB0byB0aGUgbGVkZ2VyCgllcnIgPSBzdHViLlB1dFN0YXRlKEEsIFtdYnl0ZShzdHJjb252Lkl0b2EoQXZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJZXJyID0gc3R1Yi5QdXRTdGF0ZShCLCBbXWJ5dGUoc3RyY29udi5JdG9hKEJ2YWwpKSkKCWlmIGVyciAhPSBuaWwgewoJCXJldHVybiBzaGltLkVycm9yKGVyci5FcnJvcigpKQoJfQoKCXJldHVybiBzaGltLlN1Y2Nlc3MobmlsKQp9CgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIEludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSkgcGIuUmVzcG9uc2UgewoJZm10LlByaW50bG4oImV4MDIgSW52b2tlIikKCWZ1bmN0aW9uLCBhcmdzIDo9IHN0dWIuR2V0RnVuY3Rpb25BbmRQYXJhbWV0ZXJzKCkKCWlmIGZ1bmN0aW9uID09ICJpbnZva2UiIHsKCQkvLyBNYWtlIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgoJCXJldHVybiB0Lmludm9rZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJkZWxldGUiIHsKCQkvLyBEZWxldGVzIGFuIGVudGl0eSBmcm9tIGl0cyBzdGF0ZQoJCXJldHVybiB0LmRlbGV0ZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJxdWVyeSIgewoJCS8vIHRoZSBvbGQgIlF1ZXJ5IiBpcyBub3cgaW1wbGVtdG5lZCBpbiBpbnZva2UKCQlyZXR1cm4gdC5xdWVyeShzdHViLCBhcmdzKQoJfQoKCXJldHVybiBzaGltLkVycm9yKCJJbnZhbGlkIGludm9rZSBmdW5jdGlvbiBuYW1lLiBFeHBlY3RpbmcgXCJpbnZva2VcIiBcImRlbGV0ZVwiIFwicXVlcnlcIiIpCn0KCi8vIFRyYW5zYWN0aW9uIG1ha2VzIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIGludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBYIGludCAgICAgICAgICAvLyBUcmFuc2FjdGlvbiB2YWx1ZQoJdmFyIGVyciBlcnJvcgoKCWlmIGxlbihhcmdzKSAhPSAzIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAzIikKCX0KCglBID0gYXJnc1swXQoJQiA9IGFyZ3NbMV0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJLy8gVE9ETzogd2lsbCBiZSBuaWNlIHRvIGhhdmUgYSBHZXRBbGxTdGF0ZSBjYWxsIHRvIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkZhaWxlZCB0byBnZXQgc3RhdGUiKQoJfQoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkVudGl0eSBub3QgZm91bmQiKQoJfQoJQXZhbCwgXyA9IHN0cmNvbnYuQXRvaShzdHJpbmcoQXZhbGJ5dGVzKSkKCglCdmFsYnl0ZXMsIGVyciA6PSBzdHViLkdldFN0YXRlKEIpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGdldCBzdGF0ZSIpCgl9CglpZiBCdmFsYnl0ZXMgPT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRW50aXR5IG5vdCBmb3VuZCIpCgl9CglCdmFsLCBfID0gc3RyY29udi5BdG9pKHN0cmluZyhCdmFsYnl0ZXMpKQoKCS8vIFBlcmZvcm0gdGhlIGV4ZWN1dGlvbgoJWCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMl0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW52YWxpZCB0cmFuc2FjdGlvbiBhbW91bnQsIGV4cGVjdGluZyBhIGludGVnZXIgdmFsdWUiKQoJfQoJQXZhbCA9IEF2YWwgLSBYCglCdmFsID0gQnZhbCArIFgKCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSBiYWNrIHRvIHRoZSBsZWRnZXIKCWVyciA9IHN0dWIuUHV0U3RhdGUoQSwgW11ieXRlKHN0cmNvbnYuSXRvYShBdmFsKSkpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcihlcnIuRXJyb3IoKSkKCX0KCgllcnIgPSBzdHViLlB1dFN0YXRlKEIsIFtdYnl0ZShzdHJjb252Lkl0b2EoQnZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIERlbGV0ZXMgYW4gZW50aXR5IGZyb20gc3RhdGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBkZWxldGUoc3R1YiBzaGltLkNoYWluY29kZVN0dWJJbnRlcmZhY2UsIGFyZ3MgW11zdHJpbmcpIHBiLlJlc3BvbnNlIHsKCWlmIGxlbihhcmdzKSAhPSAxIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAxIikKCX0KCglBIDo9IGFyZ3NbMF0KCgkvLyBEZWxldGUgdGhlIGtleSBmcm9tIHRoZSBzdGF0ZSBpbiBsZWRnZXIKCWVyciA6PSBzdHViLkRlbFN0YXRlKEEpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGRlbGV0ZSBzdGF0ZSIpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIHF1ZXJ5IGNhbGxiYWNrIHJlcHJlc2VudGluZyB0aGUgcXVlcnkgb2YgYSBjaGFpbmNvZGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBxdWVyeShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEgc3RyaW5nIC8vIEVudGl0aWVzCgl2YXIgZXJyIGVycm9yCgoJaWYgbGVuKGFyZ3MpICE9IDEgewoJCXJldHVybiBzaGltLkVycm9yKCJJbmNvcnJlY3QgbnVtYmVyIG9mIGFyZ3VtZW50cy4gRXhwZWN0aW5nIG5hbWUgb2YgdGhlIHBlcnNvbiB0byBxdWVyeSIpCgl9CgoJQSA9IGFyZ3NbMF0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJGYWlsZWQgdG8gZ2V0IHN0YXRlIGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJOaWwgYW1vdW50IGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJanNvblJlc3AgOj0gIntcIk5hbWVcIjpcIiIgKyBBICsgIlwiLFwiQW1vdW50XCI6XCIiICsgc3RyaW5nKEF2YWxieXRlcykgKyAiXCJ9IgoJZm10LlByaW50ZigiUXVlcnkgUmVzcG9uc2U6JXNcbiIsIGpzb25SZXNwKQoJcmV0dXJuIHNoaW0uU3VjY2VzcyhBdmFsYnl0ZXMpCn0KCmZ1bmMgbWFpbigpIHsKCWVyciA6PSBzaGltLlN0YXJ0KG5ldyhTaW1wbGVDaGFpbmNvZGUpKQoJaWYgZXJyICE9IG5pbCB7CgkJZm10LlByaW50ZigiRXJyb3Igc3RhcnRpbmcgU2ltcGxlIGNoYWluY29kZTogJXMiLCBlcnIpCgl9Cn0K",
  	"abbreviation":"中文简称"
  }
  ```

  

- 接口路径

  /system/contract/add

- 接口类型

  POST

- 接口返回

  ```json
  
  ```

  

####  5.2 修改

- 接口描述

  修改

- 接口入参请求头：

  Content-Type ：application/json

  x-userid：613463581383565312（用户id）

  ```json
  {
  	"id":"632174156993470464",
  	"contractName":"contactTest",
  	"projectId":"613322810009436160",
  	"contractDesc":"contactTest desc",
  	"fileBase64": "LyoKQ29weXJpZ2h0IElCTSBDb3JwLiAyMDE2IEFsbCBSaWdodHMgUmVzZXJ2ZWQuCgpMaWNlbnNlZCB1bmRlciB0aGUgQXBhY2hlIExpY2Vuc2UsIFZlcnNpb24gMi4wICh0aGUgIkxpY2Vuc2UiKTsKeW91IG1heSBub3QgdXNlIHRoaXMgZmlsZSBleGNlcHQgaW4gY29tcGxpYW5jZSB3aXRoIHRoZSBMaWNlbnNlLgpZb3UgbWF5IG9idGFpbiBhIGNvcHkgb2YgdGhlIExpY2Vuc2UgYXQKCgkJIGh0dHA6Ly93d3cuYXBhY2hlLm9yZy9saWNlbnNlcy9MSUNFTlNFLTIuMAoKVW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzb2Z0d2FyZQpkaXN0cmlidXRlZCB1bmRlciB0aGUgTGljZW5zZSBpcyBkaXN0cmlidXRlZCBvbiBhbiAiQVMgSVMiIEJBU0lTLApXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IgaW1wbGllZC4KU2VlIHRoZSBMaWNlbnNlIGZvciB0aGUgc3BlY2lmaWMgbGFuZ3VhZ2UgZ292ZXJuaW5nIHBlcm1pc3Npb25zIGFuZApsaW1pdGF0aW9ucyB1bmRlciB0aGUgTGljZW5zZS4KKi8KCnBhY2thZ2UgbWFpbgoKLy9XQVJOSU5HIC0gdGhpcyBjaGFpbmNvZGUncyBJRCBpcyBoYXJkLWNvZGVkIGluIGNoYWluY29kZV9leGFtcGxlMDQgdG8gaWxsdXN0cmF0ZSBvbmUgd2F5IG9mCi8vY2FsbGluZyBjaGFpbmNvZGUgZnJvbSBhIGNoYWluY29kZS4gSWYgdGhpcyBleGFtcGxlIGlzIG1vZGlmaWVkLCBjaGFpbmNvZGVfZXhhbXBsZTA0LmdvIGhhcwovL3RvIGJlIG1vZGlmaWVkIGFzIHdlbGwgd2l0aCB0aGUgbmV3IElEIG9mIGNoYWluY29kZV9leGFtcGxlMDIuCi8vY2hhaW5jb2RlX2V4YW1wbGUwNSBzaG93J3MgaG93IGNoYWluY29kZSBJRCBjYW4gYmUgcGFzc2VkIGluIGFzIGEgcGFyYW1ldGVyIGluc3RlYWQgb2YKLy9oYXJkLWNvZGluZy4KCmltcG9ydCAoCgkiZm10IgoJInN0cmNvbnYiCgoJImdpdGh1Yi5jb20vaHlwZXJsZWRnZXIvZmFicmljL2NvcmUvY2hhaW5jb2RlL3NoaW0iCglwYiAiZ2l0aHViLmNvbS9oeXBlcmxlZGdlci9mYWJyaWMvcHJvdG9zL3BlZXIiCikKCi8vIFNpbXBsZUNoYWluY29kZSBleGFtcGxlIHNpbXBsZSBDaGFpbmNvZGUgaW1wbGVtZW50YXRpb24KdHlwZSBTaW1wbGVDaGFpbmNvZGUgc3RydWN0IHsKfQoKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBJbml0KHN0dWIgc2hpbS5DaGFpbmNvZGVTdHViSW50ZXJmYWNlKSBwYi5SZXNwb25zZSB7CglmbXQuUHJpbnRsbigiZXgwMiBJbml0IikKCV8sIGFyZ3MgOj0gc3R1Yi5HZXRGdW5jdGlvbkFuZFBhcmFtZXRlcnMoKQoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBlcnIgZXJyb3IKCglpZiBsZW4oYXJncykgIT0gNCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkluY29ycmVjdCBudW1iZXIgb2YgYXJndW1lbnRzLiBFeHBlY3RpbmcgNCIpCgl9CgoJLy8gSW5pdGlhbGl6ZSB0aGUgY2hhaW5jb2RlCglBID0gYXJnc1swXQoJQXZhbCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMV0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRXhwZWN0aW5nIGludGVnZXIgdmFsdWUgZm9yIGFzc2V0IGhvbGRpbmciKQoJfQoJQiA9IGFyZ3NbMl0KCUJ2YWwsIGVyciA9IHN0cmNvbnYuQXRvaShhcmdzWzNdKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkV4cGVjdGluZyBpbnRlZ2VyIHZhbHVlIGZvciBhc3NldCBob2xkaW5nIikKCX0KCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSB0byB0aGUgbGVkZ2VyCgllcnIgPSBzdHViLlB1dFN0YXRlKEEsIFtdYnl0ZShzdHJjb252Lkl0b2EoQXZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJZXJyID0gc3R1Yi5QdXRTdGF0ZShCLCBbXWJ5dGUoc3RyY29udi5JdG9hKEJ2YWwpKSkKCWlmIGVyciAhPSBuaWwgewoJCXJldHVybiBzaGltLkVycm9yKGVyci5FcnJvcigpKQoJfQoKCXJldHVybiBzaGltLlN1Y2Nlc3MobmlsKQp9CgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIEludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSkgcGIuUmVzcG9uc2UgewoJZm10LlByaW50bG4oImV4MDIgSW52b2tlIikKCWZ1bmN0aW9uLCBhcmdzIDo9IHN0dWIuR2V0RnVuY3Rpb25BbmRQYXJhbWV0ZXJzKCkKCWlmIGZ1bmN0aW9uID09ICJpbnZva2UiIHsKCQkvLyBNYWtlIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgoJCXJldHVybiB0Lmludm9rZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJkZWxldGUiIHsKCQkvLyBEZWxldGVzIGFuIGVudGl0eSBmcm9tIGl0cyBzdGF0ZQoJCXJldHVybiB0LmRlbGV0ZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJxdWVyeSIgewoJCS8vIHRoZSBvbGQgIlF1ZXJ5IiBpcyBub3cgaW1wbGVtdG5lZCBpbiBpbnZva2UKCQlyZXR1cm4gdC5xdWVyeShzdHViLCBhcmdzKQoJfQoKCXJldHVybiBzaGltLkVycm9yKCJJbnZhbGlkIGludm9rZSBmdW5jdGlvbiBuYW1lLiBFeHBlY3RpbmcgXCJpbnZva2VcIiBcImRlbGV0ZVwiIFwicXVlcnlcIiIpCn0KCi8vIFRyYW5zYWN0aW9uIG1ha2VzIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIGludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBYIGludCAgICAgICAgICAvLyBUcmFuc2FjdGlvbiB2YWx1ZQoJdmFyIGVyciBlcnJvcgoKCWlmIGxlbihhcmdzKSAhPSAzIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAzIikKCX0KCglBID0gYXJnc1swXQoJQiA9IGFyZ3NbMV0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJLy8gVE9ETzogd2lsbCBiZSBuaWNlIHRvIGhhdmUgYSBHZXRBbGxTdGF0ZSBjYWxsIHRvIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkZhaWxlZCB0byBnZXQgc3RhdGUiKQoJfQoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkVudGl0eSBub3QgZm91bmQiKQoJfQoJQXZhbCwgXyA9IHN0cmNvbnYuQXRvaShzdHJpbmcoQXZhbGJ5dGVzKSkKCglCdmFsYnl0ZXMsIGVyciA6PSBzdHViLkdldFN0YXRlKEIpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGdldCBzdGF0ZSIpCgl9CglpZiBCdmFsYnl0ZXMgPT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRW50aXR5IG5vdCBmb3VuZCIpCgl9CglCdmFsLCBfID0gc3RyY29udi5BdG9pKHN0cmluZyhCdmFsYnl0ZXMpKQoKCS8vIFBlcmZvcm0gdGhlIGV4ZWN1dGlvbgoJWCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMl0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW52YWxpZCB0cmFuc2FjdGlvbiBhbW91bnQsIGV4cGVjdGluZyBhIGludGVnZXIgdmFsdWUiKQoJfQoJQXZhbCA9IEF2YWwgLSBYCglCdmFsID0gQnZhbCArIFgKCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSBiYWNrIHRvIHRoZSBsZWRnZXIKCWVyciA9IHN0dWIuUHV0U3RhdGUoQSwgW11ieXRlKHN0cmNvbnYuSXRvYShBdmFsKSkpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcihlcnIuRXJyb3IoKSkKCX0KCgllcnIgPSBzdHViLlB1dFN0YXRlKEIsIFtdYnl0ZShzdHJjb252Lkl0b2EoQnZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIERlbGV0ZXMgYW4gZW50aXR5IGZyb20gc3RhdGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBkZWxldGUoc3R1YiBzaGltLkNoYWluY29kZVN0dWJJbnRlcmZhY2UsIGFyZ3MgW11zdHJpbmcpIHBiLlJlc3BvbnNlIHsKCWlmIGxlbihhcmdzKSAhPSAxIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAxIikKCX0KCglBIDo9IGFyZ3NbMF0KCgkvLyBEZWxldGUgdGhlIGtleSBmcm9tIHRoZSBzdGF0ZSBpbiBsZWRnZXIKCWVyciA6PSBzdHViLkRlbFN0YXRlKEEpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGRlbGV0ZSBzdGF0ZSIpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIHF1ZXJ5IGNhbGxiYWNrIHJlcHJlc2VudGluZyB0aGUgcXVlcnkgb2YgYSBjaGFpbmNvZGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBxdWVyeShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEgc3RyaW5nIC8vIEVudGl0aWVzCgl2YXIgZXJyIGVycm9yCgoJaWYgbGVuKGFyZ3MpICE9IDEgewoJCXJldHVybiBzaGltLkVycm9yKCJJbmNvcnJlY3QgbnVtYmVyIG9mIGFyZ3VtZW50cy4gRXhwZWN0aW5nIG5hbWUgb2YgdGhlIHBlcnNvbiB0byBxdWVyeSIpCgl9CgoJQSA9IGFyZ3NbMF0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJGYWlsZWQgdG8gZ2V0IHN0YXRlIGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJOaWwgYW1vdW50IGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJanNvblJlc3AgOj0gIntcIk5hbWVcIjpcIiIgKyBBICsgIlwiLFwiQW1vdW50XCI6XCIiICsgc3RyaW5nKEF2YWxieXRlcykgKyAiXCJ9IgoJZm10LlByaW50ZigiUXVlcnkgUmVzcG9uc2U6JXNcbiIsIGpzb25SZXNwKQoJcmV0dXJuIHNoaW0uU3VjY2VzcyhBdmFsYnl0ZXMpCn0KCmZ1bmMgbWFpbigpIHsKCWVyciA6PSBzaGltLlN0YXJ0KG5ldyhTaW1wbGVDaGFpbmNvZGUpKQoJaWYgZXJyICE9IG5pbCB7CgkJZm10LlByaW50ZigiRXJyb3Igc3RhcnRpbmcgU2ltcGxlIGNoYWluY29kZTogJXMiLCBlcnIpCgl9Cn0K",
  	"abbreviation":"别名"
  }
  ```

  

- 接口路径

  /system/contract/edit

- 接口类型

  POST

- 接口返回

  ```json
  
  ```

  

### 6、合约调用记录

/monitor/call/sdk/record/page此接口返回时间精确到秒

### 7、区块信息和交易信息接口

- 接口描述

  根据区块信息和交易信息接口合成一个，先查询区块信息，有数据就返回，没有数据再查询交易信息。

  /api/monitor/blockTransaction/query
  api/monitor/blockinfo/query

  合并到/api/monitor/blockinfo/query

```json
    /*
     * @Description 先查询区块信息，有数据就返回，没有数据再查询交易信息
     * @Author xuchang
     * @Date 2019/10/10
     */
    @RequestMapping(value = "/info-and-transaction/query" ,method = RequestMethod.POST)
    @Logable
    public BusinessResult<BlockInfoAndTransactionResult> queryBlockInfoAndTransaction(
            @RequestBody BlockInfoAndTransactionQueryRequest request){
        BlockInfoAndTransactionResult blockInfoAndTransactionResult = new BlockInfoAndTransactionResult();
        //查询区块信息
        String queryParam = request.getQueryParam();
        BlockInfoQueryParam blockInfoQueryParam = new BlockInfoQueryParam();
        if(!queryParam.matches(PARAM_FORMART)){
            blockInfoQueryParam.setHash(queryParam);
        }else{
            blockInfoQueryParam.setBlockHeight( Long.parseLong(queryParam));
        }
        BusinessResult<BlockInfoResult> blockInfoResult = blockInfoService.queryBlockInfo(blockInfoQueryParam);
        if (blockInfoResult.isSuccess()){
            blockInfoAndTransactionResult.setBlockInfoResult(blockInfoResult.getData());
            return BusinessResult.success(blockInfoAndTransactionResult);
        }
        //查询区块交易信息
        BlockTransactionQueryParam blockTransactionQueryParam = new BlockTransactionQueryParam();
        blockTransactionQueryParam.setTxId(queryParam);
        BusinessResult<BlockTransactionResult> blockTransactionResult = blockTransactionService.queryBlockTransaction(blockTransactionQueryParam);
        if (blockTransactionResult.isSuccess()){
            blockInfoAndTransactionResult.setBlockTransactionResult(blockTransactionResult.getData());
        }else {
            return BusinessResult.fail(blockTransactionResult.getReturnCode(),blockTransactionResult.getReturnMsg());
        }
        return BusinessResult.success(blockInfoAndTransactionResult);
    }
```



- 接口参数
- 接口类型
- 接口路径
- 接口返回

### 8、日志分页查询

日志查询接口时间精确到秒

### 9、用户（应用）新增列表

/system/project/page-overview 接口增加部门作为条件，返回结果增加联系人和联系方式

- 接口描述

  /system/project/page-overview 接口增加部门作为条件，返回结果增加联系人和联系方式

- 接口路径

  /system/project/page-overview

- 接口入参

  ```json
  {
  	"name":"",
  	"organizationId":"619227683267555328",
  	"pageNum":1,
  	"pageSize":10,
  	"startTime":"",
  	"endTime":""
  }
  ```

  

- 接口类型

  POST

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "a52f6309e590418c9db0cbf57c2b8d66",
      "success": true,
      "data": {
          "total": 4,
          "pageCount": 1,
          "pageNum": 1,
          "pageSize": 10,
          "datas": [
              {
                  "id": "619231297407037440",
                  "number": "619231297407037440",
                  "name": "TEST",
                  "description": "TEST",
                  "organizationName": "QATB",
                  "sum": 4,
                  "createTime": "2019-09-12 15:31:54",
                  "contact": "联系人",
                  "contactPhone": "13800138001"
              },
              {
                  "id": "619230915440160768",
                  "number": "619230915440160768",
                  "name": "QATB",
                  "description": "QATB",
                  "organizationName": "QATB",
                  "sum": 3,
                  "createTime": "2019-09-12 15:31:51",
                  "contact": "联系人系",
                  "contactPhone": "13800138003"
              },
              {
                  "id": "618035918208512000",
                  "number": "618035918208512000",
                  "name": "QA",
                  "description": "QA",
                  "organizationName": "QATB",
                  "sum": 2,
                  "createTime": "2019-09-02 15:31:45",
                  "contact": "联系人",
                  "contactPhone": "13800138000"
              },
              {
                  "id": "619181279165820928",
                  "number": "619181279165820928",
                  "name": "和谐共享社区",
                  "description": "和谐共享社区",
                  "organizationName": "QATB",
                  "sum": 1,
                  "createTime": "2019-08-31 15:31:49",
                  "contact": "李延辉",
                  "contactPhone": "18789472475"
              }
          ]
      }
  }
  ```

  

### 10、调用记录增加字段 调用记录添加接口

- 接口描述：

  增加result和errorMsg字段，可为空

- 接口路径

  /system/call/sdk/record/insert

- 接口参数

  ```json
  {
  	"contractName":"contacttestab",
  	"contractVersion":"1.0",
  	"contractChannel":"合约通道",
  	"contractFcn":"method",
  	"projectName":"projectName",
  	"organizationName":"organizationName",
  	"result":"code",
  	"errorMsg":"msg"
  }
  ```

  

- 接口类型

  POST

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "3bb46563436341b58afc2f86b7434a48",
      "success": true,
      "data": true
  }
  ```

  

### 11、链上数据-业务总览

- 接口描述：

  只保留业务量，增加合约总量，合约模板数，链上文件（SYSTEM_EXIST_EVIDENCE），验真次数（SYSTEM_VERITY_TRUTH），链上数据（MONITOR_BLOCK_TRANSACTION）

- 接口入参

  ```json
  {
  	"applicationId":""
  }
  ```

  

- 接口路径

  /monitor/index/total

- 接口类型

  POST

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "c16bc94cbca74cddab770c90ee2f120f",
      "success": true,
      "data": {
          "userTotal": 6,
          "organizationTotal": 4,
          "contractCallTotal": 68,
          "contractCallTotalOnToday": 0,
          "contractCallTotalOnWeek": 0,
          "contractCallTotalOnMonth": 10,
          "contractTotal": 21,
          "projectTotal": 12,
          "projectTotalOnToday": 0,
          "projectTotalOnWeek": 0,
          "projectTotalOnMonth": 0,
          "contractTemplateTotal": 10,
          "verityTruthTotal": 3,
          "existEvidenceTotal": 3,
          "transactionChainDataTotal": 22
      }
  }
  ```

  

```java
    //合约模板
    private int contractTemplateTotal;
    //验真次数
    private int verityTruthTotal;
    //链上文件
    private int existEvidenceTotal;
    //链上数据
    private int transactionChainDataTotal;
```



### 12、模板管理

#### 12.1 条件分页查询

- 接口描述：

  模板管理，所有人都可以看到系统模板，但是个人不能编辑系统模板
  管理员可以看到所有模板，可以编辑系统模板，但是不能编辑个人模板

- 接口参数：

  ```json
  {
  	"number":"",
  	"name":"",
  	"pageNum":1,
  	"pageSize":10,
  	"roleId":"superAdmin"
  }
  roleId类型：superAdmin，ordinaryAdmin，systemAdmin，为空普通用户
  ```

  

- 接口类型

  POST

- 接口路径

  /system/template/page

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "6adb794c9b5243069d315d1f12cff866",
      "success": true,
      "data": {
          "total": 4,
          "pageCount": 1,
          "pageNum": 1,
          "pageSize": 10,
          "datas": [
              {
                  "id": "618167713155526656",
                  "number": "618167713155526656",
                  "createTime": "2019/09/02",
                  "state": "0",
                  "name": "testC",
                  "description": "testC desc",
                  "fileBase64": null,
                  "type": "system",
                  "abbreviation": "别名",
                  "userId": ""
              },
              {
                  "id": "632663778508787712",
                  "number": "632663778508787712",
                  "createTime": "2019/10/12",
                  "state": "0",
                  "name": "aaa",
                  "description": "aaa",
                  "fileBase64": null,
                  "type": "user",
                  "abbreviation": "啊啊",
                  "userId": "611256845809643520"
              },
              {
                  "id": "632607410808664064",
                  "number": "632607410808664064",
                  "createTime": "2019/10/12",
                  "state": "0",
                  "name": "abcd",
                  "description": "aaaa",
                  "fileBase64": null,
                  "type": "user",
                  "abbreviation": "AAAa1",
                  "userId": "611256845809643520"
              },
              {
                  "id": "632596035147378688",
                  "number": "632596035147378688",
                  "createTime": "2019/10/12",
                  "state": "0",
                  "name": "abc",
                  "description": "aaaa",
                  "fileBase64": null,
                  "type": "user",
                  "abbreviation": "AAAa1",
                  "userId": "611256845809643520"
              }
          ]
      }
  }
  ```

  

#### 12.1 修改模板

- 接口描述：

  模板管理，所有人都可以看到系统模板，但是个人不能编辑系统模板 管理员可以看到所有模板，可以编辑系统模板，但是不能编辑个人模板

- 接口参数：

  roleId类型：superAdmin，ordinaryAdmin，systemAdmin，为空普通用户

  ```json
  {
    "name": "testData",
    "id":"633394565260791808",
    "description": "testC desc",
    "fileBase64": "LyoKQ29weXJpZ2h0IElCTSBDb3JwLiAyMDE2IEFsbCBSaWdodHMgUmVzZXJ2ZWQuCgpMaWNlbnNlZCB1bmRlciB0aGUgQXBhY2hlIExpY2Vuc2UsIFZlcnNpb24gMi4wICh0aGUgIkxpY2Vuc2UiKTsKeW91IG1heSBub3QgdXNlIHRoaXMgZmlsZSBleGNlcHQgaW4gY29tcGxpYW5jZSB3aXRoIHRoZSBMaWNlbnNlLgpZb3UgbWF5IG9idGFpbiBhIGNvcHkgb2YgdGhlIExpY2Vuc2UgYXQKCgkJIGh0dHA6Ly93d3cuYXBhY2hlLm9yZy9saWNlbnNlcy9MSUNFTlNFLTIuMAoKVW5sZXNzIHJlcXVpcmVkIGJ5IGFwcGxpY2FibGUgbGF3IG9yIGFncmVlZCB0byBpbiB3cml0aW5nLCBzb2Z0d2FyZQpkaXN0cmlidXRlZCB1bmRlciB0aGUgTGljZW5zZSBpcyBkaXN0cmlidXRlZCBvbiBhbiAiQVMgSVMiIEJBU0lTLApXSVRIT1VUIFdBUlJBTlRJRVMgT1IgQ09ORElUSU9OUyBPRiBBTlkgS0lORCwgZWl0aGVyIGV4cHJlc3Mgb3IgaW1wbGllZC4KU2VlIHRoZSBMaWNlbnNlIGZvciB0aGUgc3BlY2lmaWMgbGFuZ3VhZ2UgZ292ZXJuaW5nIHBlcm1pc3Npb25zIGFuZApsaW1pdGF0aW9ucyB1bmRlciB0aGUgTGljZW5zZS4KKi8KCnBhY2thZ2UgbWFpbgoKLy9XQVJOSU5HIC0gdGhpcyBjaGFpbmNvZGUncyBJRCBpcyBoYXJkLWNvZGVkIGluIGNoYWluY29kZV9leGFtcGxlMDQgdG8gaWxsdXN0cmF0ZSBvbmUgd2F5IG9mCi8vY2FsbGluZyBjaGFpbmNvZGUgZnJvbSBhIGNoYWluY29kZS4gSWYgdGhpcyBleGFtcGxlIGlzIG1vZGlmaWVkLCBjaGFpbmNvZGVfZXhhbXBsZTA0LmdvIGhhcwovL3RvIGJlIG1vZGlmaWVkIGFzIHdlbGwgd2l0aCB0aGUgbmV3IElEIG9mIGNoYWluY29kZV9leGFtcGxlMDIuCi8vY2hhaW5jb2RlX2V4YW1wbGUwNSBzaG93J3MgaG93IGNoYWluY29kZSBJRCBjYW4gYmUgcGFzc2VkIGluIGFzIGEgcGFyYW1ldGVyIGluc3RlYWQgb2YKLy9oYXJkLWNvZGluZy4KCmltcG9ydCAoCgkiZm10IgoJInN0cmNvbnYiCgoJImdpdGh1Yi5jb20vaHlwZXJsZWRnZXIvZmFicmljL2NvcmUvY2hhaW5jb2RlL3NoaW0iCglwYiAiZ2l0aHViLmNvbS9oeXBlcmxlZGdlci9mYWJyaWMvcHJvdG9zL3BlZXIiCikKCi8vIFNpbXBsZUNoYWluY29kZSBleGFtcGxlIHNpbXBsZSBDaGFpbmNvZGUgaW1wbGVtZW50YXRpb24KdHlwZSBTaW1wbGVDaGFpbmNvZGUgc3RydWN0IHsKfQoKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBJbml0KHN0dWIgc2hpbS5DaGFpbmNvZGVTdHViSW50ZXJmYWNlKSBwYi5SZXNwb25zZSB7CglmbXQuUHJpbnRsbigiZXgwMiBJbml0IikKCV8sIGFyZ3MgOj0gc3R1Yi5HZXRGdW5jdGlvbkFuZFBhcmFtZXRlcnMoKQoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBlcnIgZXJyb3IKCglpZiBsZW4oYXJncykgIT0gNCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkluY29ycmVjdCBudW1iZXIgb2YgYXJndW1lbnRzLiBFeHBlY3RpbmcgNCIpCgl9CgoJLy8gSW5pdGlhbGl6ZSB0aGUgY2hhaW5jb2RlCglBID0gYXJnc1swXQoJQXZhbCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMV0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRXhwZWN0aW5nIGludGVnZXIgdmFsdWUgZm9yIGFzc2V0IGhvbGRpbmciKQoJfQoJQiA9IGFyZ3NbMl0KCUJ2YWwsIGVyciA9IHN0cmNvbnYuQXRvaShhcmdzWzNdKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkV4cGVjdGluZyBpbnRlZ2VyIHZhbHVlIGZvciBhc3NldCBob2xkaW5nIikKCX0KCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSB0byB0aGUgbGVkZ2VyCgllcnIgPSBzdHViLlB1dFN0YXRlKEEsIFtdYnl0ZShzdHJjb252Lkl0b2EoQXZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJZXJyID0gc3R1Yi5QdXRTdGF0ZShCLCBbXWJ5dGUoc3RyY29udi5JdG9hKEJ2YWwpKSkKCWlmIGVyciAhPSBuaWwgewoJCXJldHVybiBzaGltLkVycm9yKGVyci5FcnJvcigpKQoJfQoKCXJldHVybiBzaGltLlN1Y2Nlc3MobmlsKQp9CgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIEludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSkgcGIuUmVzcG9uc2UgewoJZm10LlByaW50bG4oImV4MDIgSW52b2tlIikKCWZ1bmN0aW9uLCBhcmdzIDo9IHN0dWIuR2V0RnVuY3Rpb25BbmRQYXJhbWV0ZXJzKCkKCWlmIGZ1bmN0aW9uID09ICJpbnZva2UiIHsKCQkvLyBNYWtlIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgoJCXJldHVybiB0Lmludm9rZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJkZWxldGUiIHsKCQkvLyBEZWxldGVzIGFuIGVudGl0eSBmcm9tIGl0cyBzdGF0ZQoJCXJldHVybiB0LmRlbGV0ZShzdHViLCBhcmdzKQoJfSBlbHNlIGlmIGZ1bmN0aW9uID09ICJxdWVyeSIgewoJCS8vIHRoZSBvbGQgIlF1ZXJ5IiBpcyBub3cgaW1wbGVtdG5lZCBpbiBpbnZva2UKCQlyZXR1cm4gdC5xdWVyeShzdHViLCBhcmdzKQoJfQoKCXJldHVybiBzaGltLkVycm9yKCJJbnZhbGlkIGludm9rZSBmdW5jdGlvbiBuYW1lLiBFeHBlY3RpbmcgXCJpbnZva2VcIiBcImRlbGV0ZVwiIFwicXVlcnlcIiIpCn0KCi8vIFRyYW5zYWN0aW9uIG1ha2VzIHBheW1lbnQgb2YgWCB1bml0cyBmcm9tIEEgdG8gQgpmdW5jICh0ICpTaW1wbGVDaGFpbmNvZGUpIGludm9rZShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEsIEIgc3RyaW5nICAgIC8vIEVudGl0aWVzCgl2YXIgQXZhbCwgQnZhbCBpbnQgLy8gQXNzZXQgaG9sZGluZ3MKCXZhciBYIGludCAgICAgICAgICAvLyBUcmFuc2FjdGlvbiB2YWx1ZQoJdmFyIGVyciBlcnJvcgoKCWlmIGxlbihhcmdzKSAhPSAzIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAzIikKCX0KCglBID0gYXJnc1swXQoJQiA9IGFyZ3NbMV0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJLy8gVE9ETzogd2lsbCBiZSBuaWNlIHRvIGhhdmUgYSBHZXRBbGxTdGF0ZSBjYWxsIHRvIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkZhaWxlZCB0byBnZXQgc3RhdGUiKQoJfQoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoIkVudGl0eSBub3QgZm91bmQiKQoJfQoJQXZhbCwgXyA9IHN0cmNvbnYuQXRvaShzdHJpbmcoQXZhbGJ5dGVzKSkKCglCdmFsYnl0ZXMsIGVyciA6PSBzdHViLkdldFN0YXRlKEIpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGdldCBzdGF0ZSIpCgl9CglpZiBCdmFsYnl0ZXMgPT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRW50aXR5IG5vdCBmb3VuZCIpCgl9CglCdmFsLCBfID0gc3RyY29udi5BdG9pKHN0cmluZyhCdmFsYnl0ZXMpKQoKCS8vIFBlcmZvcm0gdGhlIGV4ZWN1dGlvbgoJWCwgZXJyID0gc3RyY29udi5BdG9pKGFyZ3NbMl0pCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW52YWxpZCB0cmFuc2FjdGlvbiBhbW91bnQsIGV4cGVjdGluZyBhIGludGVnZXIgdmFsdWUiKQoJfQoJQXZhbCA9IEF2YWwgLSBYCglCdmFsID0gQnZhbCArIFgKCWZtdC5QcmludGYoIkF2YWwgPSAlZCwgQnZhbCA9ICVkXG4iLCBBdmFsLCBCdmFsKQoKCS8vIFdyaXRlIHRoZSBzdGF0ZSBiYWNrIHRvIHRoZSBsZWRnZXIKCWVyciA9IHN0dWIuUHV0U3RhdGUoQSwgW11ieXRlKHN0cmNvbnYuSXRvYShBdmFsKSkpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcihlcnIuRXJyb3IoKSkKCX0KCgllcnIgPSBzdHViLlB1dFN0YXRlKEIsIFtdYnl0ZShzdHJjb252Lkl0b2EoQnZhbCkpKQoJaWYgZXJyICE9IG5pbCB7CgkJcmV0dXJuIHNoaW0uRXJyb3IoZXJyLkVycm9yKCkpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIERlbGV0ZXMgYW4gZW50aXR5IGZyb20gc3RhdGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBkZWxldGUoc3R1YiBzaGltLkNoYWluY29kZVN0dWJJbnRlcmZhY2UsIGFyZ3MgW11zdHJpbmcpIHBiLlJlc3BvbnNlIHsKCWlmIGxlbihhcmdzKSAhPSAxIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiSW5jb3JyZWN0IG51bWJlciBvZiBhcmd1bWVudHMuIEV4cGVjdGluZyAxIikKCX0KCglBIDo9IGFyZ3NbMF0KCgkvLyBEZWxldGUgdGhlIGtleSBmcm9tIHRoZSBzdGF0ZSBpbiBsZWRnZXIKCWVyciA6PSBzdHViLkRlbFN0YXRlKEEpCglpZiBlcnIgIT0gbmlsIHsKCQlyZXR1cm4gc2hpbS5FcnJvcigiRmFpbGVkIHRvIGRlbGV0ZSBzdGF0ZSIpCgl9CgoJcmV0dXJuIHNoaW0uU3VjY2VzcyhuaWwpCn0KCi8vIHF1ZXJ5IGNhbGxiYWNrIHJlcHJlc2VudGluZyB0aGUgcXVlcnkgb2YgYSBjaGFpbmNvZGUKZnVuYyAodCAqU2ltcGxlQ2hhaW5jb2RlKSBxdWVyeShzdHViIHNoaW0uQ2hhaW5jb2RlU3R1YkludGVyZmFjZSwgYXJncyBbXXN0cmluZykgcGIuUmVzcG9uc2UgewoJdmFyIEEgc3RyaW5nIC8vIEVudGl0aWVzCgl2YXIgZXJyIGVycm9yCgoJaWYgbGVuKGFyZ3MpICE9IDEgewoJCXJldHVybiBzaGltLkVycm9yKCJJbmNvcnJlY3QgbnVtYmVyIG9mIGFyZ3VtZW50cy4gRXhwZWN0aW5nIG5hbWUgb2YgdGhlIHBlcnNvbiB0byBxdWVyeSIpCgl9CgoJQSA9IGFyZ3NbMF0KCgkvLyBHZXQgdGhlIHN0YXRlIGZyb20gdGhlIGxlZGdlcgoJQXZhbGJ5dGVzLCBlcnIgOj0gc3R1Yi5HZXRTdGF0ZShBKQoJaWYgZXJyICE9IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJGYWlsZWQgdG8gZ2V0IHN0YXRlIGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJaWYgQXZhbGJ5dGVzID09IG5pbCB7CgkJanNvblJlc3AgOj0gIntcIkVycm9yXCI6XCJOaWwgYW1vdW50IGZvciAiICsgQSArICJcIn0iCgkJcmV0dXJuIHNoaW0uRXJyb3IoanNvblJlc3ApCgl9CgoJanNvblJlc3AgOj0gIntcIk5hbWVcIjpcIiIgKyBBICsgIlwiLFwiQW1vdW50XCI6XCIiICsgc3RyaW5nKEF2YWxieXRlcykgKyAiXCJ9IgoJZm10LlByaW50ZigiUXVlcnkgUmVzcG9uc2U6JXNcbiIsIGpzb25SZXNwKQoJcmV0dXJuIHNoaW0uU3VjY2VzcyhBdmFsYnl0ZXMpCn0KCmZ1bmMgbWFpbigpIHsKCWVyciA6PSBzaGltLlN0YXJ0KG5ldyhTaW1wbGVDaGFpbmNvZGUpKQoJaWYgZXJyICE9IG5pbCB7CgkJZm10LlByaW50ZigiRXJyb3Igc3RhcnRpbmcgU2ltcGxlIGNoYWluY29kZTogJXMiLCBlcnIpCgl9Cn0K",
    "abbreviation":"别名",
    "roleId":""
  }
  ```

  

- 接口类型

  POST

- 接口路径

  /system/template/update

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "d023b3460dcf475eb828e4353b431010",
      "success": true,
      "data": true
  }
  ```

  