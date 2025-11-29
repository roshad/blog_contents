---
title: 用影刀指令通过ODBC连接MySQL

date: 2025-09-05


tags:
  - 影刀
---

- ODBC 是 **开放式数据库连接**（**Open Database Connectivity**）的缩写。 允许应用程序通过一套统一的接口访问各种不同的数据库系统（无论是 MySQL、SQL Server、还是 Oracle）。
- [下载地址](https://dev.mysql.com/downloads/connector/odbc/) ODBC需要安装和影刀<mark style="background: #FF5582A6;">相同</mark>的位数的，64位影刀就装64位ODBC，影刀【设置】--【关于影刀】可查看。
- 提供程序选择OLE DB Provider for ODBC Drivers
- [来源](https://www.yingdao.com/community/detaildiscuss?id=858652603433615360)

| 维度      | ODBC                                                     | 代码直连 (Native Driver)                                   |
| ------- | -------------------------------------------------------- | ------------------------------------------------------ |
| 跨语言/跨平台 | <span style="color:green;">☑</span> 任何支持 ODBC 的语言都能用同一 DSN | <span style="color:red;">☒</span> 每语言需各自的驱动            |
| 跨数据库    | <span style="color:green;">☑</span> 换数据库只需换驱动+改 DSN, 代码不动  | <span style="color:red;">☒</span> 换库需重写连接串, 甚至改 SQL 方言 |
| 部署便利    | <span style="color:red;">☒</span> 每台客户机需先装驱动+配 DSN       | <span style="color:green;">☑</span> 驱动随应用打包, 拷过去即跑       |
| 性能      | <span style="color:red;">☒</span> 多一层翻译, 延迟高 5~15 %      | <span style="color:green;">☑</span> 原生协议, 最快             |
| 功能完整性   | <span style="color:red;">☒</span> 仅支持 ODBC 标准, 高级特性缺失    | <span style="color:green;">☑</span> 100 % 支持数据库特有功能      |
| 安全/加密   | <span style="color:orange;">⚠️</span> 取决于驱动实现, 配置复杂      | <span style="color:green;">☑</span> 新版原生驱动默认 SSL/TLS     |
| 故障排查    | <span style="color:green;">☑</span> 系统 ODBC 管理器一键测连通性      | <span style="color:red;">☒</span> 需在代码里打日志或抓包          |
| 云/容器场景  | <span style="color:red;">☒</span> 镜像里再装系统驱动+配 DSN 麻烦     | <span style="color:green;">☑</span> 镜像里带驱动即可, 一条连接串搞定    |
- DSN 是 **Data Source Name** 的缩写，中文常译为“数据源名称”。 在 ODBC这种连接技术中，DSN 扮演着核心的角色。它不是数据库本身，而是一个**配置的名称**，这个配置包含了连接特定数据库所需的所有信息。
	- OBDC Data Source中添加的就是。