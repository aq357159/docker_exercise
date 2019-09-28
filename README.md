# docker_exercise
docker 練習

## docker images 或 docker image ls

```
  // 例1:查看映像檔
  docker images

  // 例2:查看映像檔
  docker image ls
```

## docker pull [DockerHub倉庫提供映像檔]

DockerHub倉庫URL: https://hub.docker.com/

```
  // 例子 取得ubuntu映像檔資料
  docker pull ubuntu
  // 查看映像檔
  docker images
```

## docker rmi [image名稱 or ID]

```
  // 刪除 image
  docker rmi [image名稱 or ID]
  // 查看映像檔
  docker images
```

## docker save [OPTIONS] IMAGE [IMAGE...]

```
  /*
  Options:
    -o, --output string   Write to a file, instead of STDOUT
  */
  // 匯出 image
  docker save -o ubuntu_14.04.tar ubuntu:14.04
```
## docker load [OPTIONS]

```
  /*
  Options:
    -i, --input string   Read from tar archive file, instead of STDIN
    -q, --quiet          Suppress the load output
  */
  // 匯入 image
  docker load -i [load file]
```

## docker ps [OPTIONS]

```
  /*
  Options:
    -a, --all             Show all containers (default shows just running)
    -f, --filter filter   Filter output based on conditions provided
        --format string   Pretty-print containers using a Go template
    -n, --last int        Show n last created containers (includes all
                          states) (default -1)
    -l, --latest          Show the latest created container (includes all
                          states)
        --no-trunc        Don't truncate output
    -q, --quiet           Only display numeric IDs
    -s, --size            Display total file sizes
  */

  // 查看容器
  docker ps [OPTIONS]
```

## docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

```
  //例子 建立一個ubuntu(IMAGE)有base(COMMAND)功能的容器
  // -t 選項讓Docker分配一個虛擬終端（pseudo-tty）並綁定到容器的標準輸入上
  // -i 則讓容器的標準輸入保持打開。
  docker run -it ubuntu base
  // 查看容器
  docker ps
```

## docker rm [Container(容器) ID]

```
  //  刪除 容器
  docker rm [容器ID]
  // 查看容器
  docker ps
```

## docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

```
  /*
  Options:
    -d, --detach               Detached mode: run command in the background
        --detach-keys string   Override the key sequence for detaching a
                              container
    -e, --env list             Set environment variables
    -i, --interactive          Keep STDIN open even if not attached
        --privileged           Give extended privileges to the command
    -t, --tty                  Allocate a pseudo-TTY
    -u, --user string          Username or UID (format:
                              <name|uid>[:<group|gid>])
    -w, --workdir string       Working directory inside the container
  */
  // 進入容器
  docker exec -ti [容器ID] [COMMAND]
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


