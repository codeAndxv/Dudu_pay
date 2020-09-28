## 嘟嘟Pay 商店
### 一、功能
- 商品分类管理
- 商品管理
- 卡密管理
- 固定商品管理
- 订单管理
- 生成商品跳转链接
### 二、 产品图
###### 1. 前台主页
![嘟嘟商店前台.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3uodrou6j30vm0pzwg3.jpg)
###### 2. 嘟嘟商店后台主页
![嘟嘟商店 主页.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3uhdcbw5j31h80q074x.jpg)
###### 3. 嘟嘟商店后台 配置页
![嘟嘟商店后台 配置页.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3uuz9wtbj31h30pzq3w.jpg)
###### 4. 管理商品分类
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflg9ifj31gy0po74n.jpg)
###### 5. 添加商品
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflqeojj31h80puq3h.jpg)
###### 6. 管理商品
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflboxqj31gx0pugmh.jpg)
###### 7. 添加卡密
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflb79qj31h90pv3yv.jpg)
###### 8. 管理卡密
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflbxb4j31gx0ptjsv.jpg)
###### 9. 编辑固定内容
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflc801j31h40pwglz.jpg)
###### 10. 管理订单
![](http://ww1.sinaimg.cn/large/005U6dysly1gj3wflced1j31h40pvwh2.jpg)

###  三、搭建
###### 1. 下载源码
将给你的源码上传到服务器上
###### 2. 下载宝塔
到[宝塔官网](https://www.bt.cn/)，根据是windows服务器还是linux下载对应的宝塔版本
###### 3. 下载安装
nginx、mysql、php7、phpMyAdmin、FileZilla Server
![宝塔  已安装软件.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3yze6ng2j31bw0pgaci.jpg)
###### 4. 创建网站
![宝塔  创建网站.png](http://ww1.sinaimg.cn/large/005U6dysly1gj43b8u5poj30hu0jkmxu.jpg)
按照提示，将各项逐一填写
###### 5. 配置网站
- 域名管理 确认域名填写正确， 填写两个域名，一个是前缀带www的，一个不带。
- 网站目录->网站目录 设置为public并保存
- 伪静态 设置为thinkphp并保存
- 默认文档 设置将index.html放在第一行并保存
- SSL 可以注册宝塔账号来获取SSL
###### 6. 修改数据库配置
打开源码下面的config/database.php
```
修改hostname、database、username、password这几个字段
hostname: ip地址
database: 创建网站对应的那个数据库
username：可以使用创建网站时同时创建的那个用户名，也可以使用root用户
password：用户名对应的那个密码
```
###### 7. 计划任务
访问URL，执行周期为每1分钟，访问内容为：http://域名/closeOrder

### 四、搭建和使用视频
[搭建和使用视频](https://www.bilibili.com/video/BV1Xi4y177U9?p=2)