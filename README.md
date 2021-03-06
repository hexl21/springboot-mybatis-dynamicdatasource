# This is springboot-mybatis-dynamicdatasource
- springboot+mybatis+druid+mysql实现的服务启动时加载多数据源、运行期间多数据源动态增删改、动态切换
- Druid是阿里巴巴开源平台上一个数据库连接池实现，被誉为Java语言中最好的数据库连接池，高效稳定，在大并发场景中表现很好，同时Druid不仅仅是一个数据库连接池，除了DruidDataSource之外，它还能够提供强大的监控和扩展功能。
- 数据源加载方式1（dev环境下）：服务启动时通过jdbc读取主数据库中关于数据源的配置来加载数据源，添加/修改/删除数据源时只需在主数据库中配置，然后重启服务，无需代码改动
- 数据源加载方式2（test环境下）：服务启动时通过读取配置文件(config/application-test.properties)中关于数据源的配置来加载数据源，添加/修改/删除数据源时只需在配置文件中配置，然后重启服务，无需代码改动
- 数据源动态增删改（dev环境下）：是针对数据源加载方式1的改进，在运行期间也可以动态地增加、修改、删除数据源，无需修改配置，也无需重启服务，无需代码改动

# test
- 在创建好数据库并初始化数据之后，通过swagger或者直接访问[http://localhost:8080/mybatis/getDataBases?dataSource=XXX]链接查看数据源动态切换的效果
- 通过swagger或者直接访问[http://localhost:8080/dynamic/addDataSource]就可以增加第四个数据源(得先初始化好数据库)，然后访问[http://localhost:8080/mybatis/getDataBases?dataSource=fourth]查看数据源动态切换的效果

## Guide
https://github.com/yjclsx/springboot-mybatis-dynamicdatasource.git

## What you'll need
- JDK 1.8+
- Maven 3+

## Stack
- Java
- Spring Boot

## author
- yaojiacheng