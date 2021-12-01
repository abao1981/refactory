# API接口

## API-KEY

### 获取api-key详情

需要管理员权限，可以获取自己申请的某个api-key的详情。
#### Request
- Method: **GET**
- URL:  ```/v1.0/api-key/{api-key}```
- Headers：
``` json
{
  "x-api-key": "管理员的apiKey",
}
```

#### Response
- Body
``` json
{
  "status": 1,
  "data": "b7d1c3f5e74436a94bb5a37ae0b4c2c3"
}
```

* * *

### 申请api-key

需要管理员权限，可以申请对某个实体的某个操作的api-key。
#### Request
- Method: **POST**
- URL:  ```/v1.0/api-key/apply```
- Headers：
``` json
{
  "x-api-key": "管理员的apiKey",
}
```
- Body:
``` json
{
  "entity": "group",
  "operate": "update", // 可用值：'update', 'upload', 'get', 'all'
  "items": [100, 103] // groupId的数组
}
```

#### Response
- Body
```
{
  "status": 1,
  "data": "b7d1c3f5e74436a94bb5a37ae0b4c2c3"
}
```
注意：all > upload > update > get， 前面的权限包括后面权限。


