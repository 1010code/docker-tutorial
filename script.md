
## 製作image
```bash
$ docker build -t <your username>/node-web-app .
```
## 查詢本機所有的image
```bash
$ docker images
```

## 執行image
-d 背景執行
```bash
$ docker run -p 49160:8000 -d <your username>/node-web-app

$ docker run -it -p 3000:8080 docker-node-demo bash  # 進入container bash模式，手動跑指令
```

## Print app output
```bash
docker logs <container id>
```

## 進入 container
```bash
docker exec -it <container id> /bin/bash
```

## 查詢執行中的container
```bash
$ docker ps # -a可以查尋所有詳細
```

## 刪除所有容器 Delete all containers
docker rm $(docker ps -a -q)
docker rm $(docker ps -aq)

## 刪除所有映像檔 Delete all images
docker rmi $(docker images -q)

## 刪除執行中的 container
```bash
# Get container ID
$ docker ps
CONTAINER ID        IMAGE                     COMMAND             CREATED             STATUS              PORTS                     NAMES
1e19f0cab27d        andy6804tw/node-web-app   "npm start"         7 seconds ago       Up 6 seconds        0.0.0.0:49160->8000/tcp   focused_shannon
# 使用CONTAINER ID刪除container
$ docker container kill 1e19f0cab27d 
```


# 流程
1. 建立 Dockerfile
2. build image
```bash
docker build -t 專案名稱
```
3. 進到 container 內確認檔案
可以在裡面手動執行server
```bash
docker run -it 專案名稱 bash
```
> exit 退出
