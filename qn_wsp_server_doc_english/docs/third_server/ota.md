### OTA

The Scale can upgrade via BLE or Wifi.

We will send an upgrade package to you.

And we will offer four data that you should configure it in your Server: 

+ Internal Model: The model of your device
+ Hardware Model: The chip model of your device
+ Version: The version of upgrade package
+ File Checksum(8 chars): The checksum of upgrade package

#### Show Ota Versions(App -> Your Server)

Endpoint: `POST /api/v1/ota_versions/show_ota_version`

Body Params

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|
|internal_model|string|Yes|Internal Model|mock: 029A|
|hardware_model|string|Yes|Hardware Model|mock: 0001|
|version|integer|Yes|Current Version|mock: 1|

Return Params

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|can_upgrade|boolean|Yes|Ota Versions|mock: true|
|upgrade_url|string|Yes|Upgrade Url|mock: http://your-server-domain.com/AN_URL_CAN_DOWNLOAD|

#### Read Ota Versions(Docker -> Your Server)

Endpoint: `POST /wsp/read_ota_versions`

Body Params

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|
|internal_model|string|Yes|Internal Model|mock: 029A|
|hardware_model|string|Yes|Hardware Model|mock: 0001|
|version|integer|Yes|Current Version|mock: 1|

Return Params

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|ota_versions|object []|Yes|Ota Versions|item type: object|
|├─ internal_model|string|Yes|Internal Model|mock: 029A|
|├─ hardware_model|string|Yes|Hardware Model|mock: 0001|
|├─ version|integer|Yes|Version|mock: 6|
|├─ crc|string|Yes|File Checksum(8 chars)|mock: AABBCCDD|