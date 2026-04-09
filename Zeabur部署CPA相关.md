---
tags: 
title: Zeabur部署CPA相关
date created: 260222
date modified: 260223
---
- [来源](https://linux.do/t/topic/1590730)
- 定时重启，重启时会拉取最新镜像。
- Watchtower在zeabur无用，因zeabur基于k8s而非docker。但平台AI还是会错误推荐使用watchtower。

# 部署步骤
- 官方模板无用
-  一、创建项目-选择共享集群 - 免费试用集群
# 二、进入项目部署新服务

### 1.选择Docker容器镜像

### 自定义prebuilt
- ***镜像***：`eceasy/cli-proxy-api:latest`
- ***环境变量***：变量名：`DEPLOY`，值：`cloud`，
- ***端口***：`8317` HTTP
- ***挂载卷***：ID随意，路径`/data`
- ***启动命令***：`/CLIProxyAPI/CLIProxyAPI --config /data/config.yaml`

> 都配置完后点击部署，等待显示为`运行中`

- 三、设定域名 - 点击`添加域名`-`生成域名`-填个喜欢的名字-`确认绑定`
> 

## 四、配置文件

### 1. 在 服务状态页面的 文件 中新建配置

### 2. 在data目录下新建config.yaml

> **(不要切换V2)点击新建文件，输入`../data/config.yaml`——回车** ，**要看到左侧目录的data目录下有这个文件，如果没有也可以返回再重新进入一下。**
> 

### 3. 写入官方实践给的最简化配置,点击保存

```yaml
port: 8317
remote-management:
  allow-remote: true
  secret-key: "改"
  disable-control-panel: false
auth-dir: "/data/auths"
debug: false
logging-to-file: false
usage-statistics-enabled: false
request-retry: 3
quota-exceeded:
   switch-project: true
   switch-preview-model: true
```

### 4. 回到服务状态页面，重启当前版本

### 五、登陆后台，Enjoy！！

### 输入网址`https://你的自定义域名.zeabur.app/management.html#/login`

重启之后几分钟，才能正常访问。

> baseurl：[https://你的自定义域名.zeabur.app](https://xn--7iq6zi6i0tenvfe32cvxq.zeabur.app/)
> 
> 
> apikey：config.yaml里的api-keys
> 

这里也是几分钟之后才能正常请求。