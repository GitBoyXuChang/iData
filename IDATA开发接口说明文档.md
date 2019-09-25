# IDATA开发接口说明文档

## 链上数据

### 1、业务总览

#### 1.1 累计、当月、本周、当日

路径：

http://127.0.0.1:8090/index/total

/monitor/index/total

请求类型 POST

请求参数：

```json
{
	"applicationId":""
}
```

相应参数：

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "b9c503b056174fa2bd56ec0c269d0bc9",
    "success": true,
    "data": {
        "userTotal": 6,
        "organizationTotal": 0,
        "contractCallTotal": 52,
        "contractCallTotalOnToday": 1,
        "contractCallTotalOnWeek": 17,
        "contractCallTotalOnMonth": 52,
        "contractTotal": 13,
        "contractUpgradeTotal": 3,
        "contractTotalOnToday": 0,
        "contractUpgradeTotalOnToday": 0,
        "contractTotalOnWeek": 0,
        "contractUpgradeTotalOnWeek": 0,
        "contractTotalOnMonth": 10,
        "contractUpgradeTotalOnMonth": 3,
        "projectTotal": 6,
        "projectTotalOnToday": 0,
        "projectTotalOnWeek": 1,
        "projectTotalOnMonth": 5
    }
}
```

说明：

```java
//用户数
    private Integer userTotal;
    //部门数
    private Integer organizationTotal;
    //合约调用量总量
    private Integer contractCallTotal;
    //当天合约调用量
    private Integer contractCallTotalOnToday;
    //当周合约调用量
    private Integer contractCallTotalOnWeek;
    //当月合约调用量
    private Integer contractCallTotalOnMonth;
    //合约总量
    private Integer contractTotal;
    //合约升级量总量
    private Integer contractUpgradeTotal;
    //当天合约上传量
    private Integer contractTotalOnToday;
    //当天合约升级量
    private Integer contractUpgradeTotalOnToday;
    //当周合约上传量
    private Integer contractTotalOnWeek;
    //当周合约升级量
    private Integer contractUpgradeTotalOnWeek;
    //当月合约上传量
    private Integer contractTotalOnMonth;
    //当月合约升级量
    private Integer contractUpgradeTotalOnMonth;
    //应用总量
    private int projectTotal;
    //当天新增应用量
    private int projectTotalOnToday;
    //当周新增应用量
    private int projectTotalOnWeek;
    //当月新增应用量
    private int projectTotalOnMonth;
```

#### 1.2 合约调用量分布

路径：

http://127.0.0.1:8090/call/sdk/record/project/total

/monitor/call/sdk/record/project/total

请求类型 GET

请求参数：无

```json

```

相应参数：

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "5bb5aa2d227049ffb7a2db07fa0e87a2",
    "success": true,
    "data": [
        {
            "projectName": "QA",
            "count": 33
        },
        {
            "projectName": "QATB",
            "count": 13
        },
        {
            "projectName": "QB",
            "count": 3
        },
        {
            "projectName": "QC",
            "count": 2
        },
        {
            "projectName": "QQB",
            "count": 1
        }
    ]
}
```

说明：

#### 1.3 业务量分布

路径：

http://127.0.0.1:8090/call/sdk/record/organization/total

/monitor/call/sdk/record/organization/total

请求类型 GET

请求参数：无

```json

```

相应参数：

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "61030e11d2a748129364fc7871e6fba3",
    "success": true,
    "data": [
        {
            "organizationName": "QA",
            "count": 4
        },
        {
            "organizationName": "QATB",
            "count": 4
        }
    ]
}
```

说明：

#### 1.4 各业务合约调用量统计图

路径：

http://127.0.0.1:8090/call/sdk/record/bargraph/total

/monitor/call/sdk/record/bargraph/total

请求类型 POST

请求参数：当前时间往后推day

```json
{
	"day":5
}
```

相应参数：

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "ef91dc354569456ca4d1ece81a43003d",
    "success": true,
    "data": [
        {
            "date": "20190920",
            "barGraphResults": [
                {
                    "contractName": "QA",
                    "count": 4
                },
                {
                    "contractName": "和谐共享社区",
                    "count": 0
                },
                {
                    "contractName": "QATB",
                    "count": 0
                },
                {
                    "contractName": "TEST",
                    "count": 0
                },
                {
                    "contractName": "项目7",
                    "count": 0
                },
                {
                    "contractName": "项目8",
                    "count": 0
                }
            ]
        },
        {
            "date": "20190921",
            "barGraphResults": [
                {
                    "contractName": "QA",
                    "count": 0
                },
                {
                    "contractName": "和谐共享社区",
                    "count": 0
                },
                {
                    "contractName": "QATB",
                    "count": 0
                },
                {
                    "contractName": "TEST",
                    "count": 0
                },
                {
                    "contractName": "项目7",
                    "count": 0
                },
                {
                    "contractName": "项目8",
                    "count": 0
                }
            ]
        },
        {
            "date": "20190922",
            "barGraphResults": [
                {
                    "contractName": "QA",
                    "count": 0
                },
                {
                    "contractName": "和谐共享社区",
                    "count": 0
                },
                {
                    "contractName": "QATB",
                    "count": 0
                },
                {
                    "contractName": "TEST",
                    "count": 0
                },
                {
                    "contractName": "项目7",
                    "count": 0
                },
                {
                    "contractName": "项目8",
                    "count": 0
                }
            ]
        },
        {
            "date": "20190923",
            "barGraphResults": [
                {
                    "contractName": "QA",
                    "count": 0
                },
                {
                    "contractName": "和谐共享社区",
                    "count": 0
                },
                {
                    "contractName": "QATB",
                    "count": 1
                },
                {
                    "contractName": "TEST",
                    "count": 0
                },
                {
                    "contractName": "项目7",
                    "count": 0
                },
                {
                    "contractName": "项目8",
                    "count": 0
                }
            ]
        },
        {
            "date": "20190924",
            "barGraphResults": [
                {
                    "contractName": "QA",
                    "count": 2
                },
                {
                    "contractName": "和谐共享社区",
                    "count": 0
                },
                {
                    "contractName": "QATB",
                    "count": 12
                },
                {
                    "contractName": "TEST",
                    "count": 0
                },
                {
                    "contractName": "项目7",
                    "count": 0
                },
                {
                    "contractName": "项目8",
                    "count": 0
                }
            ]
        },
        {
            "date": "20190925",
            "barGraphResults": [
                {
                    "contractName": "QA",
                    "count": 1
                },
                {
                    "contractName": "和谐共享社区",
                    "count": 0
                },
                {
                    "contractName": "QATB",
                    "count": 0
                },
                {
                    "contractName": "TEST",
                    "count": 0
                },
                {
                    "contractName": "项目7",
                    "count": 0
                },
                {
                    "contractName": "项目8",
                    "count": 0
                }
            ]
        }
    ]
}
```

说明：



### 2、合约统计