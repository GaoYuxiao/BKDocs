
### 请求方法

POST


### 请求地址

/api/c/compapi/v2/sops/start_task/


### 通用参数

| 字段 | 类型 | 必选 |  描述 |
|-----------|------------|--------|------------|
| bk_app_code  |  string    | 是 | 应用ID     |
| bk_app_secret|  string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -> 点击应用ID -> 基本信息 获取 |
| bk_token     |  string    | 否 | 当前用户登录态，bk_token与bk_username必须一个有效，bk_token可以通过Cookie获取 |
| bk_username  |  string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |


### 功能描述

开始执行任务

### 请求参数

#### 接口参数

| 字段          |  类型       | 必选   |  描述             |
|---------------|------------|--------|------------------|
|   bk_biz_id   |   string     |   是   |  模板所属业务ID |
|   task_id     |   string     |   是   |  任务ID         |
| scope | string | 否 | bk_biz_id 检索的作用域。默认为 cmdb_biz，此时检索的是绑定的 CMDB 业务 ID 为 bk_biz_id 的项目；当值为 project 时则检索项目 ID 为 bk_biz_id 的项目|

### 请求参数示例

```
{
    "bk_app_code": "esb_test",
    "bk_app_secret": "xxx",
    "bk_token": "xxx",
    "bk_username": "xxx",
    "bk_biz_id": "2",
    "task_id": "10",
    "scope": "cmdb_biz"
}
```

### 返回结果示例

```
{
    "result": true,
    "task_url": "http://paas_url/taskflow/execute/xxx/?instance_id=xxx",
    "data": {
            "task_url": task_url
    },
    "code": 3545100,
    "request_id": "xxx",
    "trace_id": "xxx"
}
```

### 返回结果参数说明

| 字段      | 类型      | 描述      |
|-----------|----------|-----------|
|  result      |    bool    |      true/false 操作是否成功     |
|  data        |    dict  |      result=true 时返回数据      |
|  message     |    string  |      result=false 时错误信息     |
|  task_url    |    string  |      任务对应的url  |
|  request_id     |    string  |      esb 请求 id     |
|  trace_id     |    string  |      open telemetry trace_id     |