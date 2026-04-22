---
name:  springboot 结构计划专家
description: 负责 Java 后端服务项目结构搭建
version: "0.1.0"
author: thm
---

# 创建 SpringBoot 项目结构

1.项目结构如下：
```
your-project-name/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── company/
│   │   │           └── project/
│   │   │               ├── ProjectApplication.java  # 启动类（必须放根目录）
│   │   │               ├── config/        # 配置类：Swagger、MyBatis、Redis、线程池等
│   │   │               ├── controller/    # 控制层：接口入口，参数校验，返回封装
│   │   │               ├── service/       # 业务逻辑层
│   │   │               │   ├── impl/      # 业务实现类（核心代码）
│   │   │               │   └── facade/    # 微服务：对外提供的接口层（单体可省略）
│   │   │               ├── mapper/        # 数据访问层：DAO，MyBatis-Plus/Mapper接口
│   │   │               ├── entity/        # 数据库实体 & 业务对象
│   │   │               │   ├── po/        # Persistent Object：数据库表映射实体
│   │   │               │   ├── dto/       # Data Transfer Object：接口入参
│   │   │               │   ├── vo/        # View Object：接口出参
│   │   │               │   ├── bo/        # Business Object：业务层内部对象（可选）
│   │   │               │   └── query/     # 分页/查询参数封装（可选）
│   │   │               ├── common/        # 全局公共模块
│   │   │               │   ├── constant/  # 常量类
│   │   │               │   ├── enums/     # 枚举类
│   │   │               │   ├── result/    # 统一返回结果封装
│   │   │               │   └── exception/ # 全局异常、自定义异常
│   │   │               ├── util/          # 工具类：日期、加密、Excel、Http等
│   │   │               └── component/     # 通用组件：定时任务、工具Bean、监听器
│   │   └── resources/
│   │       ├── application.yml           # 主配置文件
│   │       ├── application-dev.yml        # 开发环境
│   │       ├── application-test.yml       # 测试环境
│   │       ├── application-prod.yml      # 生产环境
│   │       ├── mapper/                    # MyBatis XML文件（如果用MyBatis-Plus可无）
│   │       ├── static/                    # 静态资源：js、css、图片
│   │       └── templates/                 # 模板引擎页面（前后端分离一般不用）
│   └── test/                              # 单元测试
│       └── java/
│           └── com/
│               └── company/
│                   └── project/
│                       ├── controller/    # 接口测试
│                       ├── service/       # 业务测试
│                       └── mapper/        # DAO测试
├── pom.xml                                # Maven依赖管理
└── .gitignore                             # Git忽略文件
```
2.你根据项目现在有的结构，创建我没有的结构，请自行添加。
3.如果有的结构请不要替换（必须）
4.要根据本项目的结构的名称进行命名，请自行修改。


