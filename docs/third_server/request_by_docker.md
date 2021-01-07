### General Command

#### Read Secret Key

Endpoint: `POST /wsp/read_secret_key`

Body Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|

Return Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|secret_key|string|Yes|Secret key of scale (16 charaters, blank must be '')|mock: 123456789ABCDEFG|

### 0x20

#### Read Scale Users

Endpoint: `POST /wsp/read_scale_users`

Body Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|

Return Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|scale_users|object []|Yes|Scale Users(blank is [])|item type: object|
|├─ user_index|integer|Yes|User Index(1-8)|mock: 2|
|├─ gender|integer|Yes|Gender 0 female 1 male|mock: 1|
|├─ height|number|Yes|Height(cm, keep a decimal fraction)|mock: 180.5|
|├─ birthday|string|Yes|Birthday(YYYY-mm-dd format)|mock: 1990-01-01|
|├─ user_key|integer|Yes|User Key(1000-9999)|mock: 1234|
|unit|integer|Yes|Unit 1 kg 2 lb 4 斤|mock: 1|

#### (made to order) Read Bow Scale Users

Endpoint: `POST /wsp/read_bow_scale_users`

Body Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|
|battery_level|string|YES|Battery Level 0-Disabled 1-Low 2-Working 4-Full|mock: 1|

Return Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|scale_users|object []|Yes|Scale Users(blank is [])|item type: object|
|├─ user_index|integer|Yes|User Index(1-8)|mock: 2|
|├─ gender|integer|Yes|Gender 0 female 1 male|mock: 1|
|├─ height|number|Yes|Height(cm, keep a decimal fraction)|mock: 180.5|
|├─ birthday|string|Yes|Birthday(YYYY-mm-dd format)|mock: 1990-01-01|
|├─ user_key|integer|Yes|User Key(1000-9999)|mock: 1234|
|unit|integer|Yes|Unit 1 kg 2 lb 4 斤|mock: 1|
|ctrl|integer|Yes|1 means display, 0 means hidden # Bit0->username Bit1->BMI Bit2->bone Bit3->bodyfat Bit4->sinew Bit5->water Bit6->heart rate Bit7->weather Bit8->weight-trend|mock: 511|

#### Read Ota Versions

Endpoint: `POST /wsp/read_ota_versions`

Body Params

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|

Return Params

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|ota_versions|object []|Yes|Ota Versions|item type: object|
|├─ internal_model|string|Yes|Internal Model|mock: 029A|
|├─ hardware_model|string|Yes|Hardware Model|mock: 0001|
|├─ version|integer|Yes|Version|mock: 6|
|├─ crc|string|Yes|File Checksum(8 chars)|mock: AABBCCDD|

### 0x21

#### Create Unknown Measurement

Endpoint: `POST /wsp/create_unknown_measurement`

Body Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|
|model_id|string|Yes|Model ID(4 chars)|mock: 0E2B|
|weight|number|Yes|Weight|mock: 50.0|
|timestamp|integer|Yes|Timestamp(Seconds)|mock: 1582698882|
|heart_rate|integer|Yes|Heart Rate|mock: 93|
|resistance|integer|Yes|50k Resistance|mock: 500|
|sec_resistance|integer|Yes|500k Resistance|mock: 500|
|hmac|string|Yes|Signature(Hmac)|mock: Hmac|

Return Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|is_success|boolean|Yes|Is Success|mock: true|


#### Create Measurement

Endpoint: `POST /wsp/create_measurement`

Body Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|
|model _id|string|Yes|Model ID|mock: 00EA|
|user_index|integer|Yes|User Index|mock: 1|
|weight|number|Yes|Weight|mock: 50.0|
|timestamp|integer|Yes|Timestamp(Seconds)|mock: 1582698882|
|heart_rate|integer|Yes|Heart Rate|mock: 93|
|resistance|integer|Yes|50k Resistance|mock: 500|
|sec_resistance|integer|Yes|500k Resistance|mock: 500|
|bmi|integer|Yes|BMI|mock: 21.1|
|bodyfat|number|Yes|Body Fat|mock: 27.6|
|body_shape|integer|Yes|Body Shape|mock: 4|
|fat_free_weight|number|Yes|Fat Free Weight|mock: 39.11|
|subfat|number|Yes|Subcutaneous Fat|mock: 25.8|
|visfat|integer|Yes|Visceral Fat Level|mock: 4|
|water|number|Yes|Body Water|mock: 49.7|
|muscle|number|Yes|Skeletal Muscle|mock: 42.2|
|sinew|number|Yes|Muscle Mass|mock: 36.75|
|bone|number|Yes|Bone Mass (inorganic salt)|mock: 2.35|
|protein|number|Yes|Protein|mock: 16.98|
|bmr|integer|Yes|BMR|mock: 1214|
|bodyage|integer|Yes|Body Age|mock: 27|
|score|number|Yes|Score|mock: 91.9|
|cardiac_index|number|Yes|Cardiac Index|mock: 2.7|
|hmac|string|Yes|Signature(Hmac)|mock: sfsfsffdsvsdvsd|

Return Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|is_success|boolean|Yes|Is Success|mock: true|

### 0x22

#### Finish Info Sync

Endpoint: `POST /wsp/finish_info_sync`

Body Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|mac|string|Yes|MAC|mock: 12:34:56:78:9A:BC|

Return Params:

|Name|Type|Required|Remark|Other|
|--- |--- |--- |--- |--- |
|is_success|boolean|Yes|Is Success|mock: true|
