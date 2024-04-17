# Pages搭建VLESS优选订阅链接生成器 Pages-Vless-USB

### 通过 Cloudflare Pages 搭建VLESS 节点订阅，自动生成优选线路订阅内容生成器

**Telegram交流群：[@OneZyhCN](https://t.me/OneZyhCN)    Telegram全能搜索：[@BingCN](https://t.me/BingCN)**

### 免责声明

本声明适用于 GitHub 上的 “Edgetunnel” 项目（以下简称“该项目”），项目链接为：
[https://edgetunnel.github.io/edgetunnel/](https://github.com/cmliu/edgetunnel)

https://github.com/cmliu/WorkerVless2sub/tree/main

该项目为Edgetunnel项目的克隆整理及备份，原作者享有本项目内容的所有权；
该项目被设计和开发仅供学习、研究和安全测试目的。
它旨在为安全研究者、学术界人士和技术爱好者提供一个了解和实践网络通信技术的工具。

# Workers 部署方法 [关注博主](https://www.youtube.com/@onezyhcn)

### 1. 部署 Cloudflare Pages：

   - 在 Cloudflare 控制台中创建一个新的 Pages。
   - 将 [worker.zip](https://github.com/Onezyh/Pages-Vless-USB/blob/master/worker.zip)  的文件上传到 Pages中。


### 2. 在Pages项目中设置你的专属UUID：

 - 在Cloudflare打开刚刚所创建的Pages中打开设置选项，选择【环境变量】选项，点击【添加变量】。
 - 变量名称：UUID
 - 变量值：你生成的UUID
 - UUID值可通过UUID在线生成或V2rayN进行生成；


 **3 再次上传你所下载资产文件**
 
 - 在Cloudflare打开刚刚所创建的Pages中打开设置选项，选择【部署选项】，点击最下方的【创建新的部署】；
 - 在【创建新的部署】选项中再次上传第一次部署时所下载的资产文件
 -  [worker.zip](https://github.com/Onezyh/Pages-Vless-USB/blob/master/worker.zip)  

# 订阅生成器 使用方法[关注博主](https://www.youtube.com/@onezyhcn)

  例如您的workers项目域名为：`sub.onezyhcn.workers.dev`；
  
### 1. 快速订阅

   - 添加 `TOKEN` 变量，快速订阅访问入口，默认值为: `auto` ，获取订阅器默认节点订阅地址即 `/auto` ，例如：
     ```url
     https://sub.onezyhcn.workers.dev/auto
     ```
     
### 2. 自定义订阅 

   - **自定义订阅格式** `https://[你的Workers域名]/sub?host=[你的Vless域名]&uuid=[你的UUID]&path=[你的ws路径]`
   - **host**：您的 VLESS 伪装域名，例如 `edgetunnel-2z2.pages.dev`；
   - **uuid**：您的 VLESS 客户端 UUID，例如 `30e9c5c8-ed28-4cd9-b008-dc67277f8b02`；
   - **path**（可选）：您的 VLESS 的 WS 路径（没有可留空不填），例如 `/?ed=2048`。
   - 自定义订阅地址如下：
     ```url
     https://sub.onezyhcn.workers.dev/sub?host=edgetunnel-2z2.pages.dev&uuid=30e9c5c8-ed28-4cd9-b008-dc67277f8b02&path=/?ed=2048
     ```
   - 注意路径必须包含 "/sub"。

### 3. 指定 clash、singbox 配置文件

   - 添加 `format=clash` 键值，获取 clash 订阅配置，例如：
     ```url
     https://sub.onezyhcn.workers.dev/auto?format=clash
     https://sub.onezyhcn.workers.dev/sub?format=clash&host=edgetunnel-2z2.pages.dev&uuid=30e9c5c8-ed28-4cd9-b008-dc67277f8b02&path=/?ed=2048
     ```
     
   - 添加 `format=singbox` 键值，获取 singbox 订阅配置，例如：
     ```url
     https://sub.onezyhcn.workers.dev/auto?format=singbox
     https://sub.onezyhcn.workers.dev/sub?format=singbox&host=edgetunnel-2z2.pages.dev&uuid=30e9c5c8-ed28-4cd9-b008-dc67277f8b02&path=/?ed=2048
     ```
     
### 变量说明
| 变量名 | 示例 | 备注 | 
|--------|---------|-----|
| TOKEN | auto | 快速订阅内置节点的订阅路径地址 /auto | 
| HOST | edgetunnel-2z2.pages.dev | 快速订阅内置节点的伪装域名 | 
| UUID | 30e9c5c8-ed28-4cd9-b008-dc67277f8b02 | 快速订阅内置节点的UUID | 
| PATH | /?ed=2048 | 快速订阅内置节点的路径信息 | 
| TGTOKEN | 6894123456:XXXXXXXXXX0qExVsBPUhHDAbXXXXXqWXgBA | 发送TG通知的机器人token | 
| TGID | 6946912345 | 接收TG通知的账户数字ID | 
| SUBAPI | api.v1.mk | clash、singbox等 订阅转换后端 | 


