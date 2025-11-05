 # 预备:    
               Linux(知道一些命令例如cd、mkdir即可)、SpringBoot, 上手门槛不高
               Xshell
               DockerHub
               先会使用命令, 再理解命令
               官方文档
           
 - Docker是什么   
              * Docker是一个开源的应用容器引擎, 可以配环境, 可以跨平台(相当于仓库、应用商店)
              * (环境部署, 每一个机器都要部署环境, 费时费力, 使用Docker省时省力)
              * Docker的核心思想是集装箱(看它的logo ~ )

 - Docker安装(看官方文档即可)
   镜像(image)         可以创建容器   
   容器(container)
   仓库(repository)    

 - Docker命令: 镜像命令、容器命令、操作命令......
               Docker的常用命令: 
                                   *  帮助命令 docker version      #显示Docker的版本信息
                                              docker info          #显示Docker的系统信息
                                              docker 命令 --help   #万能命令
                                   *  镜像命令(docker images 查看本地所有主机镜像)   
                                              docker rmi -f  镜像id               #删除指定的镜像
                                              docker rmi -f  镜像id 镜像id 镜像id  #删除多个镜像
                                              docker rmi -f $(docker images -aq)  #删除全部的镜像
                                              -a  显示所有镜像         all  
                                              -q  只显示镜像的ID       quiet
                                              -aq 显示所有的镜像
                                              docker search  搜索镜像
                                              docker pull    下载镜像      

                                   *  容器命令(有了镜像才可以创建容器) 
                                              docker run [可选参数] image   新建容器并启动     可选参数(-d 后台方式运行 || -it 使用交互方式运行, 进入容器查看内容  ||  -P 指定容器的端口  || -p 随机指定端口)
                                              docker ps 列出运行的容器     -a 列出当前正在运行的容器, 带出历史运行过的容器
                                              exit    退出容器             Ctrl + P + Q 容器停止不退出
                                              docker rm 容器ID   删除指定的容器           docker rm -f $(docker ps -aq)   删除所有的容器       docker ps -a -qixargs docker rm   删除所有的容器
                                              docker start  容器ID     启动容器
                                              docker restart  容器ID     重启容器
                                              docker stop  容器ID   停止当前正在运行的容器
                                              docker kill  容器ID   强制停止当前的容器
                                              docker compose  定义运行多容器 
                                   
                                    *  常用的其他命令 
                                              后台启动容器
                                              docker logs -f -t --tail 容器, 没有日志        - tf 显示日志         --tail number 显示日志条数
                                              docker top 容器ID        查看容器中的进程命令
                                              docker inspect 容器ID    查看容器的元数据
                                              docker exec -it 容器ID bashShell  进入当前正在运行的容器             docker attach 容器ID
                                              docker cp 容器ID: 容器路径   目的主机路径      从容器内拷贝文件到主机上
                                              
 - 部署Nginx 
       搜索镜像  search
       下载镜像  pull
       启动镜像  -d 后台运行
       端口暴露   expose 



 - Docker镜像



 - 容器数据卷




 - Dockerfile
   Docker是一个用 Go 语言实现的开源项目  快速部署
            - Dockerfile 是一个文本文件, 用于构建Docker镜像    Dockerfile 可以提高部署效率    Dockerfile的内容在编译之后生成的可执行程序是image
            - 构建镜像  docker build -t jekyll-begin .
            - 运行容器  docker run -p 4000:4000 jekyll-begin
            - FROM     #制作基准镜像        FROM 镜像 
            - WORKDIR  #类似于Linux中的cd命令   但是和cd不一样的地方在于, 若输入的目录在不存在, 则WORKDIR会自动创建这个目录, 再进入该目录   
            - RUN      #运行
            - CI/CD    #指持续集成和持续交付/部署     在软件开发过程中自动化构建、测试和部署的流程


   编写Dockerfile的注意事项:
                             * 最常用的五个参数: 1. FROM
                                                2. WORKDIR
                                                3. COPY
                                                4. RUN
                                                5. CMD
                             * 文件的命名必须是Dockerfile, 不能是其他, D大写
                             * 除了FROM, 其他都是非必须的
                             * EXPOSE     指定当前镜像暴露出来的端口
                               VOLUME     指定映射文件的, 一般是映射到匿名卷
                               docker run 中的 -p 和 -v 是分别指定映射到外部的端口和目录
                               ENV        指定当前容器的环境变量
                               ARG        构建参数, 运行时无效, 可以构建时临时修改变量
                               LABEL      指定元数据, 便于找到 Docker
                               USER       设置运行用户



 - Docker网络原理




 - IDEA整合Docker



 - Docker Compose




 - Docker Swarm



 - CI\CD Jenkins



2025.7.21 周一  
最近做了个 Docker 训练营, 其实不太明白, 这些命令和抽象的网络管理有什么联系? 会了命令, 不理解怎么做怎么用(当前的问题)  
外国的课抽象, 思维转换不了, 不做了



