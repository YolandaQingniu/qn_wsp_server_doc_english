# Deploy Server Docker

Server SDK is a docker image. Developer need to understand Docker.

## Generate Dockerfile
`vim Dockerfile`
```Dockerfile
FROM registry.cn-shenzhen.aliyuncs.com/yolanda/wsp_open:v1.0.10
```

## Configure Environment Variables
`vim main.env`
```
# [Required] Third Server URL
WSP_DOMAIN=http://wsp-demo.yolanda.hk

# [Optional] Authorization header, default to nil
AUTHORIZATION="Basic ZHVtbXk6MTIzNDU2Nzg="

# [Optional] Custom OTA Server, default to Yolanda OTA Sever
CUSTOM_OTA_SERVER=http://wsp-demo.yolanda.hk

# [Optional] Custom Alogrithm, default to 01
CUSTOM_ALGORITHM=01

# [Optional] Listen port, default to 3000
PORT=3000

# [Optional] Timezone, default to Asia/Shanghai
TZ=Asia/Shanghai
```

## Run Docker Container
```shell
docker build . -t wsp_server
docker run --env-file main.env wsp_server
# docker run --env-file main.env wsp_server -d # Start on background
```
