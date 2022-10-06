## 系统说明

> meta 基于 pig4cloud 构建

- 基于 Spring Cloud 2021 、Spring Boot 2.7、 OAuth2 的 RBAC **权限管理系统**
- 基于数据驱动视图的理念封装 element-plus，即使没有 vue 的使用经验也能快速上手
- 提供对常见容器化支持 Docker、Kubernetes、Rancher2 支持
- 提供 lambda 、stream api 、webflux 的生产实践

### 核心依赖

| 依赖                   | 版本         |
| ---------------------- |------------|
| Spring Boot            | 2.7.3      |
| Spring Cloud           | 2021.0.4   |
| Spring Cloud Alibaba   | 2021.0.4.0 |
| Spring Authorization Server | 0.3.1      |
| Mybatis Plus           | 3.5.2      |
| hutool                 | 5.8.7      |
| Avue                   | 3.1.3      |

### 模块说明

```lua
meta
├── meta-auth -- 授权服务提供[3000]
└── meta-common -- 系统公共模块
     ├── meta-common-bom -- 全局依赖管理控制
     ├── meta-common-core -- 公共工具类核心包
     ├── meta-common-datasource -- 动态数据源包
     ├── meta-common-job -- xxl-job 封装
     ├── meta-common-log -- 日志服务
     ├── meta-common-mybatis -- mybatis 扩展封装
     ├── meta-common-seata -- 分布式事务
     ├── meta-common-security -- 安全工具类
     ├── meta-common-swagger -- 接口文档
     └── meta-common-feign -- feign 扩展封装
├── meta-register -- Nacos Server[8848]
├── meta-gateway -- Spring Cloud Gateway网关[9999]
└── meta-upms -- 通用用户权限管理模块
     └── meta-upms-api -- 通用用户权限管理系统公共api模块
     └── meta-upms-biz -- 通用用户权限管理系统业务处理模块[4000]
└── meta-visual
     └── meta-monitor -- 服务监控 [5001]
     ├── meta-codegen -- 图形化代码生成 [5002]
     ├── meta-sentinel-dashboard -- 流量高可用 [5003]
     └── meta-xxl-job-admin -- 分布式定时任务管理台 [5004]
```

### 定制自己的微服务

[meta DIY](https://pig4cloud.com/#/common/diy)

[meta ARCHETYPE](https://pig4cloud.com/#/common/archetype)

### Docker 运行

```
# 下载并运行服务端代码
git clone https://github.com/loveylwforever/meta.git

cd meta && mvn clean install && docker-compose up -d
```
