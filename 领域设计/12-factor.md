# 12 factor design

[引用来源](https://12factor.net/zh_cn/)

## 基准代码

一份代码，多份部署

## 依赖

现实声明依赖关系

## 配置

在环境（环境变量...)中存储配置。环境是变化的，所以程序中依赖的配置，可以随着环境变化而变化。

## 后端服务

把后端服务当成附加资源，DB，cache和第三方接口都当成是一种服务资源。服务可以不修改代码的情况下，切换资源。

## 构建，发布，运行

严格分离构建和运行

## 进程

以一个或多个无状态进程运行应用

## 端口绑定

通过端口绑定提供服务

## 并发

通过进程模型进行扩展，通过多进程的方式将应用功能拆分，使得应用更有利于水平扩容，而不依赖垂直扩容。

## 易处理

快速启动和优雅终止可最大化健壮性（*优雅终止，提供程序退出的接口，在收到退出信号后进行资源清理并退出程序*）

## 开发环境与线上环境等价

尽可能的保持开发，预发布，线上环境相同

## 日志

把日志当作事件流，**应用本身从不考虑存储自身的输出流**。不应该是图去写或则管理日志文件，每一个运行的进程都会直接的标准输出（stdout）时间流。开发环境时，开发人员可以直接在终端上看到输出流。在生产环境上，每个进程的输出流由运行环境捕获，并将其他输出流整体在一起，由最终的处理程序归档。

## 管理进程

后台管理任务当作一次性进程运行，进程模型。相较于多线程，进程模型更易隔离。
