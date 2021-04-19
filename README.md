
项目说明

<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]


<!-- PROJECT LOGO -->
<br />

<p align="center">
  <a href="https://github.com/fuchuangxin/media">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">微信公众号采集系统</h3>
  <p align="center">
      系统基于LNMP平台，采用Yii2.0框架，实现了微信公众号自动解析、搜狗公众号解析、自动关注、自动采集、文章列表回采、点赞数阅读数采集、数据报表导出、数据监控功能。
    <br />
    <a href="https://github.com/fuchuangxin/media"><strong>项目介绍 »</strong></a>
    <br />
    <br />
    <a href="https://github.com/fuchuangxin/media">系统截图</a>
    ·
    <a href="https://github.com/fuchuangxin/mediae/issues">报告Bug</a>
    ·
    <a href="https://github.com/fuchuangxin/media/issues">提出新特性</a>
  </p>

</p>


 
## 目录
- [系统介绍](#系统介绍)
- [技术方案](#技术方案)
  - [微信文章采集](#微信文章采集)
  - [阅读点赞数据采集](#阅读点赞数采集)
  - [快报文章采集](#快报文章采集)
- [系统截图](#系统截图)
  - [系统首页](#系统首页)
  - [手机管理](#手机管理)
  - [微信管理](#微信管理)
  - [文章管理](#文章管理)
  - [监控管理](#监控管理)
  - [数据库展示](#数据库展示)
  - [榜单数据](#榜单数据)

- [技术栈](#技术栈)
- [作者](#作者)


### 系统介绍
 系统基于LNMP平台，采用Yii2.0框架，实现了微信公众号自动解析、搜狗公众号解析、自动关注、自动采集、文章列表回采、点赞数阅读数采集、数据报表导出、数据监控功能。为政务系统提供微信公众号指数榜单和媒探平台提供数据来源。支撑了2w+公众号和累计1KW+文章的信息数据采集工作。

### 技术方案
##### 微信文章采集
###### 手机+按键精灵+Fiddler
   通过手机代理然后按键精灵打开固定数据页然后跳转采集公众号固定页获取公众号的 `uni`然后通过代理的 `fiddler script`转发到后端PHP接口，接口将采集到的 `uni`推送到对应`uni`收集池.后端`PHP`脚本通过`Gearman`实现任务委派分发到采集队列中通过
微信接口模拟的方式爬取微信文章数据。
![image](https://github.com/fuchuangxin/meitan/blob/main/images/wechat_capture_archture.jpg)
###### 微信网页端+Fiddler
   谷歌浏览器设置代理登录微信网页客户端，结合谷歌浏览器定时刷新扩展插件，再通过`Fiddler script`脚本匹配接口数据转发到PHP后端接口进行采集。 
###### 微信移动客户端+Xposed
    微信安卓客户端通过Xposed插件hook微信接口然后转发到PHP后端接口。
###### 微信PC端+Dll注入
    微信PC客户端通过`dll`注入和易语hook微信接口然后转发到PHP后端接口。

### 系统功能
###### 系统首页
![image](https://github.com/fuchuangxin/meitan/blob/main/images/index.png)

###### 手机管理
![image](https://github.com/fuchuangxin/meitan/blob/main/images/mobile.png)
![image](https://github.com/fuchuangxin/meitan/blob/main/images/mobile_add.png)


###### 微信管理
![image](https://github.com/fuchuangxin/meitan/blob/main/images/articles.png)
![image](https://github.com/fuchuangxin/meitan/blob/main/images/article_parse_account.png)
![image](https://github.com/fuchuangxin/meitan/blob/main/images/sougou_parse_account.png)


###### 文章管理
![image](https://github.com/fuchuangxin/meitan/blob/main/images/article_list.png)


###### 监控管理
![image](https://github.com/fuchuangxin/meitan/blob/main/images/log_monitor.png)
![image](https://github.com/fuchuangxin/meitan/blob/main/images/service_monitor.png)



###### 数据库展示
![image](https://github.com/fuchuangxin/meitan/blob/main/images/kuaibao_artile_data.png)
![image](https://github.com/fuchuangxin/meitan/blob/main/images/wechat_article_data.png)


###### 榜单数据
![image](https://github.com/fuchuangxin/meitan/blob/main/images/zhengwu_excel_data.png)
![image](https://github.com/fuchuangxin/meitan/blob/main/images/account_excel_export.png)



### 技术栈
- [yii2](https://github.com/yiisoft/yii2)
- [yii2-adminlte3](https://github.com/ishizune/yii2-adminlte3)
- [gearman]()
- [mitmproxy]()
- [xposed]()
- [supervisord]()


### 作者
  QQ: 一一四七三二零五
  
<!-- links -->
[your-project-path]:fuchuangxin/media
[contributors-shield]: https://img.shields.io/github/contributors/fuchuangxin/media.svg?style=flat-square
[contributors-url]: https://github.com/fuchuangxin/media/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/fuchuangxin/media.svg?style=flat-square
[forks-url]: https://github.com/fuchuangxin/media/network/members
[stars-shield]: https://img.shields.io/github/stars/fuchuangxin/media.svg?style=flat-square
[stars-url]: https://github.com/fuchuangxin/media/stargazers
[issues-shield]: https://img.shields.io/github/issues/fuchuangxin/media.svg?style=flat-square
[issues-url]: https://img.shields.io/github/issues/fuchuangxin/media.svg
[license-shield]: https://img.shields.io/github/license/fuchuangxin/media.svg?style=flat-square
[license-url]: https://github.com/fuchuangxin/media/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555



