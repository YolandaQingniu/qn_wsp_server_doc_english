### Scale Users

#### Apply Key

Endpoint: `POST /api/v1/scale_users/apply_key`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|
|user_id|String|Yes|User ID|

Return Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|key|String|Yes|Key|

Request Example:

```json
{
  "mac": "12:34:56:78:9A:BC",
  "user_id": 100
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
    "key": 7181
  }
}
```

#### Create Scale User

Endpoint: `POST /api/v1/scale_users/create_scale_user`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|
|user_id|String|Yes|User ID|
|index|Integer|Yes|User Index|
|key|Integer|Yes|Key|

Return Params:
None

Request Example:

```json
{
  "mac": "F7:53:C8:C5:2B:86",
  "user_id": 200,
  "index": 7,
  "key": 200
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
  }
}
```

#### Delete Scale User

Endpoint: `POST /api/v1/scale_users/delete_scale_user`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|
|scale_user_ids|String|Yes|Scale User IDs, split by comma|

Return Params:
None

Request Example:

```json
{
  "mac": "12:34:56:78:9A:BC",
  "scale_user_ids": "100,100"
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
  }
}
```

#### List Need Delete User

Endpoint: `GET /api/v1/scale_users/list_need_delete_user`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|

Return Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|scale_users|Array|Yes|Scale Users|

Request Example:

```json
{
  "mac": "12:34:56:78:9A:BC"
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
    "scale_users": [
      {
        "scale_user_id": "200",
        "user_id": "200",
        "mac": "12:34:56:78:9A:BC",
        "index": 2,
        "key": 9999
      }
    ]
  }
}
```

#### List Scale User

Endpoint: `GET /api/v1/scale_users/list_scale_user`

Body Params: None

Return Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|scale_users|Array|Yes|Scale Users|

Request Example: None

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
    "scale_users": [
      {
        "scale_user_id": "200",
        "user_id": "200",
        "mac": "12:34:56:78:9A:BC",
        "index": 2,
        "key": 9999
      },
      {
        "scale_user_id": "100",
        "user_id": "100",
        "mac": "12:34:56:78:9A:BC",
        "index": 1,
        "key": 1000
      }
    ]
  }
}
```

### WSP Scale

#### Apply Network Info

Endpoint: `POST /api/v1/scales/apply_network_info`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|
|scale_name|String|Yes|Scale Name|
|internal_model|String|Yes|Internal Model|

Return Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|server_url|String|Yes|Server URL|
|ota_url|String|Yes|Ota URL|
|secret_key|String|Yes|Secret Key|

Request Example:

```json
{
  "mac": "F7:53:C8:C5:2B:86",
  "scale_name": "QN-Scale",
  "internal_model": "0152"
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
    "server_url": "http://wsp.yolanda.hk:80/wifi_api/wsps?code=",
    "ota_url": "https://otaurl.yolanda.hk",
    "secret_key": "OQnuVdVk8zH5vTmb"
  }
}
```

#### Check Firmware Version

Endpoint: `GET /api/v1/scales/check_firmware_version`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|
|internal_model|String|Yes|Internal Model|
|hardware_model|Integer|Yes|Hardware Model|
|current_firmware_version|Integer|Yes|Current Firmware Version|

Return Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|new_firmware_version_flag|Integer|Yes|Is New Firmware Version Present?|

Request Example:

```json
{
  "mac": "12:34:56:78:9A:BC",
  "internal_model": "0001",
  "hardware_model": 2,
  "current_firmware_version": 2
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
    "new_firmware_version_flag": 1
  }
}
```

#### Update Secret Key

Endpoint: `POST /api/v1/scales/update_secret_key`

Body Params:

|Name|Type|Required|Remark|
|-|-|-|-|
|mac|String|Yes|MAC|
|secret_key|String|Yes|Secret Key|

Return Params:
None

Request Example:

```json
{
  "mac": "12:34:56:78:9A:BC",
  "secret_key": "ti3FaD4bKcP3lQI2"
}
```

Response Example:

```json
{
  "code": "200",
  "msg": "ok",
  "data": {
  }
}
```
