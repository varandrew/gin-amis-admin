<h1 align="center">Gin-Amis-Admin</h1>

<div align="center">
 基于 GIN + AMIS + GORM/MONGO + CASBIN + WIRE 实现的RBAC权限管理脚手架，目的是提供一套轻量的中后台开发框架，方便、快速的完成业务需求的开发。
<br/>

![Language](https://img.shields.io/badge/language-goland1.4-blue.svg)
[![License][license-image]][license-url]

</div>

## 特性

- 遵循 `RESTful API` 设计规范 & 基于接口的编程规范
- 基于 `GIN` 框架，提供了丰富的中间件支持（JWTAuth、CORS、RequestLogger、RequestRateLimiter、TraceID、CasbinEnforce、Recover、GZIP）
- 基于 `Casbin` 的 RBAC 访问控制模型 -- **权限控制可以细粒度到按钮 & 接口**
- 基于 `Gorm/Mongo` 的数据库存储 -- 存储层抽象了标准的外部业务层调用接口，内部采用封闭式实现（为后续切换数据存储提供了较大的便利）
- 基于 `WIRE` 的依赖注入 -- 依赖注入本身的作用是解决了各个模块间层级依赖繁琐的初始化过程
- 基于 `Logrus & Context` 实现了日志输出，通过结合 Context 实现了统一的 TraceID/UserID 等关键字段的输出(同时支持日志钩子写入到`Gorm/Mongo`)
- 基于 `JWT` 的用户认证 -- 基于 JWT 的黑名单验证机制
- 基于 `Swaggo` 自动生成 `Swagger` 文档 -- 独立于接口的 mock 实现
- 基于 `net/http/httptest` 标准包实现了 API 的单元测试
- 基于 `go mod` 的依赖管理(国内源可使用：<https://goproxy.cn/>)
- 基于 `snowflake` 生成唯一ID

## 依赖工具

```
go get -u github.com/cosmtrek/air
go get -u github.com/google/wire/cmd/wire
go get -u github.com/swaggo/swag/cmd/swag
```

- [air](https://github.com/cosmtrek/air) -- Live reload for Go apps
- [wire](https://github.com/google/wire) -- Compile-time Dependency Injection for Go
- [swag](https://github.com/swaggo/swag) -- Automatically generate RESTful API documentation with Swagger 2.0 for Go.

## 依赖框架

- [Gin](https://gin-gonic.com/) -- The fastest full-featured web framework for Go.
- [GORM](http://gorm.io/) -- The fantastic ORM library for Golang
- [Mongo](https://github.com/mongodb/mongo-go-driver) -- The Go driver for MongoDB
- [Casbin](https://casbin.org/) -- An authorization library that supports access control models like ACL, RBAC, ABAC in Golang
- [Wire](https://github.com/google/wire) -- Compile-time Dependency Injection for Go

## 快速开始

[在线预览](http://amis.tanjiancheng.top:10088/#/dashboard)
> 域名已失效，请先绑定host   
> 123.207.62.203 amis.tanjiancheng.top 

测试用户名：root

测试密码：root

> 二进制包执行

[https://github.com/tanjiancheng/gin-amis-admin/releases](https://github.com/tanjiancheng/gin-amis-admin/releases)
下载对应的平台版本执行启动命令
```
# linux/drawin
make start
# windows
双击start.bat
```

> 源码执行
```bash
$ go get -u -v github.com/tanjiancheng/gin-amis-admin/cmd/gin-admin
$ cd $GOPATH/src/github.com/LyricTian/gin-admin
# 使用AIR工具运行
$ air
# OR 基于Makefile运行
$ make start
# OR 使用go命令运行
$ go run cmd/gin-admin/main.go web -c ./configs/config.toml -m ./configs/model.conf --menu ./configs/menu.yaml --page ./configs/page_manager.yaml
```

> 启动成功之后，可在浏览器中输入地址进行访问：[http://127.0.0.1:10088](http://127.0.0.1:10088)


## 特别感谢

```
本项目主要参考了:
https://github.com/baidu/amis
https://github.com/LyricTian/gin-admin
```


## MIT License

    Copyright (c) 2020

[reportcard-url]: https://goreportcard.com/report/github.com/LyricTian/gin-admin
[reportcard-image]: https://goreportcard.com/badge/github.com/LyricTian/gin-admin
[godoc-url]: https://godoc.org/github.com/LyricTian/gin-admin
[godoc-image]: https://godoc.org/github.com/LyricTian/gin-admin?status.svg
[license-url]: http://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/npm/l/express.svg
