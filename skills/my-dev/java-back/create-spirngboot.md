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


# 规范
1. 启动类（根目录）
ProjectApplication.java：SpringBoot 唯一入口，必须放在最外层包路径
作用：自动扫描子包所有 Bean（Controller/Service/Config 等）
2. config（配置层）
存放所有第三方配置、框架配置：
Swagger/Knife4j 接口文档配置
MyBatis/MyBatis-Plus 配置
Redis 配置
线程池、异步配置
CORS 跨域配置
拦截器配置
3. controller（控制层）
只做三件事：
接收前端请求参数
参数校验
调用 Service，返回统一封装结果
不写业务逻辑！
不操作数据库！
4. service（业务层）
接口：定义业务方法
impl：核心业务逻辑实现（事务、校验、调用 Mapper、组合逻辑）
企业原则：所有业务逻辑必须写在 ServiceImpl
5. mapper（数据访问层）
只和数据库交互：增删改查
MyBatis/Mapper 接口
不写业务逻辑
6. entity（数据模型分层，企业必分）
这是企业级和普通项目最大区别：分层对象，解耦前端 / 数据库 / 业务
PO：和数据库表一一对应（禁止直接返回给前端）
DTO：前端传给后端的参数
VO：后端返回给前端的数据
BO：业务内部组合对象（复杂业务用）
7. common（全局公共）
constant：系统常量
enums：状态枚举（如订单状态、性别）
result：统一返回体 Result<T>
exception：全局异常处理器 + 自定义异常
8. util（工具类）
静态工具方法：日期、加密、Http、Excel、校验等
9. resources 配置
application.yml 多环境隔离（dev/test/prod）
mapper/：MyBatis XML 文件


