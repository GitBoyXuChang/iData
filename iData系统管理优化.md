## iData系统管理优化

### 1、模板管理

#### 1.1 条件分页查询

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
      "startTime":"20190115190421",
      "endTime":"20191015190421",
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

  

#### 1.1 修改模板

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

  

### 2、证书管理

#### 2.1 证书条件分页查询

- 接口描述

  添加查询申请日期，颁发日期

- 接口路径

  /system/cert/page

- 接口类型

  POST

- 接口入参

  ```json
  {
  	"number":"",
  	"projectId":"",
  	"pageNum":1,
  	"pageSize":10,
  	"startApplyTime":"20190115190421",申请时间-开始
  	"endApplyTime":"20191015190421",申请时间-结束
  	"startAwardTime":"20190115190421",颁发时间-开始
  	"endAwardTime":"20191015190421"颁发时间-结束
  }
  ```

  

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "9367c7401bf548fc9de29b7d6cfd7cd5",
      "success": true,
      "data": {
          "total": 4,
          "pageCount": 1,
          "pageNum": 1,
          "pageSize": 10,
          "datas": [
              {
                  "id": "633392450790510592",
                  "number": "633392450790510592",
                  "projectId": "633392340727779328",
                  "applyTime": "2019/10/14",
                  "awardTime": "2019/10/14",
                  "state": "0"
              },
              {
                  "id": "627152353317224448",
                  "number": "627152353317224448",
                  "projectId": "618035918208512000",
                  "applyTime": "2019/09/27",
                  "awardTime": "2019/09/27",
                  "state": "1"
              },
              {
                  "id": "623193440326524928",
                  "number": "623193440326524928",
                  "projectId": "619181279165820928",
                  "applyTime": "2019/09/16",
                  "awardTime": "2019/09/16",
                  "state": "0"
              },
              {
                  "id": "623192907079491584",
                  "number": "623192907079491584",
                  "projectId": "618035918208512000",
                  "applyTime": "2019/09/16",
                  "awardTime": "2019/09/16",
                  "state": "2"
              }
          ]
      }
  }
  ```

  

### 3、项目管理

#### 3.1 项目分页条件查询

- 接口描述

  添加查询创建日期

- 接口路径

  /system/project/page

- 接口类型

- POST

- 接口入参

  ```JSON
  {
      "name":"",
      "organizationId":"",
      "contact":"",
      "contactPhone":"13800138000",
      "startTime":"20190115190421",
      "endTime":"20191015190421",
      "pageNum":1,
      "pageSize":10
  }
  ```

  

- 接口返回

  ```JSON
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "9c886e2261594617a98fc0ea113fb7ae",
      "success": true,
      "data": {
          "total": 3,
          "pageCount": 1,
          "pageNum": 1,
          "pageSize": 10,
          "datas": [
              {
                  "id": "626080036625387520",
                  "number": "626080036625387520",
                  "name": "项目7",
                  "description": "msg",
                  "organizationId": "618494327940722688",
                  "contact": "联系人12",
                  "contactPhone": "13800138000",
                  "host": "http://192.168.0.1",
                  "sum": 5,
                  "ipAddress": "ip",
                  "userId": "1",
                  "createTime": "2019/09/21"
              },
              {
                  "id": "626081893557014528",
                  "number": "626081893557014528",
                  "name": "项目test",
                  "description": "msg",
                  "organizationId": "613693156692680704",
                  "contact": "联系人112",
                  "contactPhone": "13800138000",
                  "host": "http://192.168.0.1",
                  "sum": 6,
                  "ipAddress": "ip",
                  "userId": "1",
                  "createTime": "2019/09/22"
              },
              {
                  "id": "627152618674061312",
                  "number": "627152618674061312",
                  "name": "项目9",
                  "description": "msg",
                  "organizationId": "613693156692680704",
                  "contact": "联系人111",
                  "contactPhone": "13800138000",
                  "host": "http://192.168.0.1",
                  "sum": 7,
                  "ipAddress": "ip",
                  "userId": "1",
                  "createTime": "2019/09/27"
              }
          ]
      }
  }
  ```

  

### 4、合约管理

#### 4.1 合约分页条件查询

- 接口描述

  添加查询创建日期

- 接口路径

  /system/contract/query

- 接口类型

- POST

- 接口入参

  ```json
  {
  	"projectId":"",
  	"number":"",
  	"state":"",
  	"abbreviation":"",
  	"startTime":"20191001095349",
      "endTime":"20191016095404",
  	"pageNum":1,
  	"pageSize":10
  }
  ```

  

- 接口返回

  ```json
  {
      "returnCode": "0000",
      "returnMsg": "Success",
      "nonceStr": "a07a0341a3904404942162358c423624",
      "success": true,
      "data": {
          "total": 3,
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
              }
          ]
      }
  }
  ```

  

### 5、日志管理

#### 5.1 日志分页条件查询

- 接口描述

  添加查询创建日期,用户id，来源ip

- 接口路径

  /system/journal/page

- 接口类型

- POST

- 接口入参

  ```json
  {
      "startTime":"20191001101925",
      "endTime":"20191016101949",
      "type":"",
      "userId":"633388202556149760",
      "content":"",
      "sourceIp":"192.168.0",
      "pageNum":1,
      "pageSize":10
  }
  ```

  

- 接口返回

```json
{
    "returnCode": "0000",
    "returnMsg": "Success",
    "nonceStr": "d37d66c1d6d14f6fb2e1282ee16bc5d1",
    "success": true,
    "data": {
        "total": 2,
        "pageCount": 1,
        "pageNum": 1,
        "pageSize": 10,
        "datas": [
            {
                "id": "633392340916523008",
                "operateTime": "2019/10/14 19:55:02",
                "type": "operate",
                "content": "应用上链",
                "userId": "633388202556149760",
                "sourceIp": "192.168.0.14",
                "operateState": "0"
            },
            {
                "id": "633380613256658944",
                "operateTime": "2019/10/14 19:08:26",
                "type": "invoke",
                "content": "合约调用记录",
                "userId": "633388202556149760",
                "sourceIp": "192.168.0.248",
                "operateState": "0"
            }
        ]
    }
}
```

