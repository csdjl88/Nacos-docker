## docker-compose 部署


## 准备工作

- 安装docker
- 安装docker-compose
- 安装git
- 安装mysql
- 安装redis
- 安装php8.2
- 安装composer

## 配置步骤

- 下载代码到hyperf目录，在hyperf目录执行`composer install --ignore-platform-reqs`
- 修改 复制项目根目录下的`.env.example`文件为`.env` 
- 并修改文件中mysql连接信息
- 修改env中的redis连接信息
- 修改env中的rabbitmq连接信息
- 修改env中的nacos连接信息

## 安装步骤
- 当前目录执行 `docker-compose up -d`
- 访问 http://localhost:15672 进行RabbitMQ测试
- 访问 http://localhost:8848/nacos 进行Nacos测试
- 访问 http://localhost:9501 进行Hyperf测试
- 当前根目录执行 docker cp ./data/rabbitmq/plugins/rabbitmq_delayed_message_exchange-3.13.0.ez rabbitmq:/plugins/rabbitmq_delayed_message_exchange-3.13.0.ez
- 当前根目录执行 docker exec -it rabbitmq rabbitmq-plugins enable rabbitmq_delayed_message_exchange
