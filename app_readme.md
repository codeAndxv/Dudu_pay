## 嘟嘟Pay 支付监控 移动端
### 一、功能
- 扫码配置
    扫描支付监控服务器端的配置二维码
- 手动配置
    手动输入支付监控服务器端的配置数据
- 检测心跳
    这个用于检测与服务器端是否正常连接
- 检测监听
    这个用于测试是否能正常读取到通知栏的信息
### 二、 产品图
###### 1. 嘟嘟Pay监控 移动端主页
![嘟嘟Pay监控 移动端主页.png](http://ww1.sinaimg.cn/large/005U6dysly1gj45eslrhwj30k00vmwfy.jpg)

### 三、搭建
移动端的安装很简单，将给你的app安装在安卓手机上即可。

### 四、App设置
- 点击检测监听  这个一般不会出现问题，如果这一步出现问题，请联系我
- 通过扫码配置或者手动配置来输入`嘟嘟Pay 支付监控 服务器端`的监控设置里面的配置数据。
- 点击检测心跳， 测试配置是否正确，app是否能连接到服务器。


### 五、手机设置
##### 1. 手机设置
首先你明白支付监控移动端是做什么用的，才能根据自己的安卓机的情况修改对应的配置。

支付监控移动端是通过监控通知栏上支付宝和微信的到款信息，向支付监控服务器发送通知。
也就是说要保证支付宝、微信和监控app三者都时时刻刻保证在后台运行。

安卓手机需要对下面的设置进行修改，包括但不限于

- 手机性能改成非省电模式
- 开启支付宝、微信的到账通知
    这一条会根据手机品牌不同，有不同的配置
- 将手机设置成永不休眠

