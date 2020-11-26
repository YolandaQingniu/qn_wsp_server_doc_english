# Deploy Server Docker

Server SDK is a docker image. Developer need to understand Docker.

## Generate Dockerfile
`vim Dockerfile`
```Dockerfile
FROM registry.cn-shenzhen.aliyuncs.com/yolanda/wsp_open:v1.0.9
```

## Configure Environment Variables
`vim main.env`
```
WSP_DOMAIN=http://wsp-demo.yolanda.hk         # [Required] Third Server URL
AUTHORIZATION="Basic ZHVtbXk6MTIzNDU2Nzg="    # [Optional] Authorization header, default to nil
CUSTOM_OTA_SERVER=http://wsp-demo.yolanda.hk  # [Optional] Custom OTA Server, default to Yolanda OTA Sever
CUSTOM_ALGORITHM=01                           # [Optional] Custom Alogrithm, default to 01
PORT=3000                                     # [Optional] Listen port, default to 3000
TZ=Asia/Shanghai                              # [Optional] Timezone, default to Asia/Shanghai
```

## Run Docker Container
```shell
docker build . -t wsp_server
docker run --env-file main.env wsp_server
# docker run --env-file main.env wsp_server -d # Start on background
```
