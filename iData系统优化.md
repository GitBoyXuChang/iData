# iData系统优化



### 1、项目管理接口优化：

描述：项目管理表(SYSTEM_PROJECT)，添加IP_ADDRESS字段；

新增项目，修改项目的接口增加ipAddress字段；

#### 1.1 添加项目

- 接口描述

添加项目

- 接口入参

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

**l** **接口入参**

| 字段名称           | 字段类型 | 是否必填 | 备注     |
| ------------------ | -------- | -------- | -------- |
| **name**           | String   | 否       | 项目名称 |
| **organizationId** | String   | 否       | 部门ID   |
| **pageSize**       | Integer  | 是       | 分页参数 |
| **pageNum**        | Integer  | 是       | 分页参数 |

 

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

模板表增加字段；

添加模板接口：增加abbreviation中文字段

添加模板接口：存储请求头userId

查询模板只展示系统模板和当前项目所属的模板（根据请求头userId）

 

### 5、合约管理

合约表新增字段；

添加合约接口：增加abbreviation中文字段

合约查询：根据请求头userId查找所属的项目，进行查询。

 

### 6、合约调用记录

/monitor/call/sdk/record/page此接口返回时间精确到秒

### 7、区块信息和交易信息接口

- 接口描述

  根据区块信息和交易信息接口合成一个，先查询区块信息，有数据就返回，没有数据再查询交易信息。

  /api/monitor/blockTransaction/query
  api/monitor/blockinfo/query

  合并到/api/monitor/blockinfo/query

```json
/**
     * @Description 根据txid查询区块交易
     * @Author zouhuanghui
     * @Date 2019/9/19
     * @return
     */
    @RequestMapping(value = "/query" ,method = RequestMethod.GET)
    @Logable
    @BusinessParamsValidate(argsIndexs = {0})
    public BusinessResult<BlockTransactionResult> queryBlockTransaction(@RequestParam(value = "txId",required = false)@NotBlank(message = "Monitor023") String txId){
        BlockTransactionQueryParam blockTransactionQueryParam = new BlockTransactionQueryParam();
        blockTransactionQueryParam.setTxId(txId);
        return  blockTransactionService.queryBlockTransaction(blockTransactionQueryParam);
    }
```



- 接口参数
- 接口类型
- 接口路径
- 接口返回

### 8、日志分页查询

日志查询接口时间精确到秒

9、

10、

4) 

5) 

6) /system/project/page-overview 接口增加部门作为条件，返回结果增加联系人和联系方式

 

7) 日志查询接口时间精确到秒

8) 

9) 超级管理员能重置密码

10) 

11) 登录接口返回用户信息和角色信息对象

默认三个角色信息