# docker_exercise
docker 練習

## docker pull [DockerHub倉庫提供映像檔]

DockerHub倉庫URL: https://hub.docker.com/

```
  // 例子 取得ubuntu映像檔資料
  docker pull ubuntu
```

## docker run -it ubuntu base

```
  //例子 建立一個ubuntu 跟base 功能
  docker run -it ubuntu base
```

## docker rm [Container(容器) ID]

```
  //  刪除 容器
  docker rm [容器ID]
```


## docker file create

自己建立映像檔
來源:https://philipzheng.gitbooks.io/docker_practice/content/image/create.html

```
  // 請先建立一個資料夾 裡面再建立一個檔案(Dockerfile)沒有副檔名
  // cd [進入該資料夾]
  docker build -t="[自訂名稱]" .
  // 檢查是否建立成功
  docker image ls
  // 刪除image 
  docker rmi [image名稱 or ID]
-----------------------------------------------------------------------
  //docker file 內容
  // # 井符號 註解
  // FROM 指令告訴 Docker 使用哪個映像檔作為基底
  // RUN 開頭的指令會在建立中執行，比如安裝一個套件
  FROM ubuntu:latest
  FROM node:latest
  MAINTAINER Docker Nathan <nathan@docker.com> // 維護者的信息
```


