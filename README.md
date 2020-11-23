## wordpress_blog
docker-compose 创建个人博客

### 目录结构：

    wordpress_blog
        docker-compose.yml

### docker-compose.yml中
    
    version: '3.3'
    
    services:
       db:
         image: mysql:5.7
         volumes:
           - db_data:/var/lib/mysql
         restart: always
         environment:
           MYSQL_ROOT_PASSWORD: somewordpress
           MYSQL_DATABASE: wordpress
           MYSQL_USER: wordpress
           MYSQL_PASSWORD: wordpress

      wordpress:
        depends_on:
          - db
        image: wordpress:latest
        ports:
          - "8000:80"
        restart: always
        environment:
          WORDPRESS_DB_HOST: db:3306
          WORDPRESS_DB_USER: wordpress
          WORDPRESS_DB_PASSWORD: wordpress
          WORDPRESS_DB_NAME: wordpress
    volumes:
        db_data: {}
       
### 创建过程
+ 安装docker，自行百度安装，本处不在赘述
+ 创建wordpress_blog过程
　　

+ 等待docker-compose运行，最终会下载mysql镜像和wordpress镜像，并部署服务

　　

+ 使用docker ps查看运行进程，会发现开启了两个进程

+ 去浏览器访问,注意ip和port

　　

　　

+ 访问后台：http://192.168.99.100:8000/admin/ 注册，填写账号和密码，即可进入后台页面，wordpress后台展示为以下：

　　

　　

+ 到了这一步，可以修改设置，发表博客，可以更改dashbord,仪表盘，设置主题，更改语言为简体中文，更改时区。后台创建你的博客，前台访问博客内容。

+ 在后台中设置你的博客和写博客，

+ 前台中查看发表的博客：通过访问http://192.168.99.100:8000/

　　
+ 此处为本人已经设置ok和写入的博客。

+ 至此，就随意在你的wordpress博客中畅游吧，欢迎点赞和关注

　　
