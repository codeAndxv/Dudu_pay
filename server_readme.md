## 嘟嘟Pay 支付监控服务器端

### 一、功能

- 收款二维码管理
- 收款二维码识别
- 订单管理
- 补单（对实际已经收到款的订单，却被标成过期的订单进行手动补单）

### 二、产品图
###### 1. 嘟嘟Pay监控 服务器端 后台主页
![嘟嘟Pay监控 服务器端 后台主页.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3ww4e3icj31gu0pi0tc.jpg)
###### 2. 嘟嘟Pay监控 服务器端 系统设置
![嘟嘟Pay监控 服务器端 系统设置.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xiy0h3gj31go0ps40g.jpg)
###### 3. 嘟嘟Pay监控 服务器端 监控端设置
![嘟嘟Pay监控 服务器端 监控端设置.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xgs6jk4j31h40powf1.jpg)
###### 4. 嘟嘟Pay监控 服务器端 微信二维码添加
![嘟嘟Pay监控 服务器端 微信二维码添加.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xjj24xjj31h30pit8z.jpg)
###### 5. 嘟嘟Pay监控 服务器端 微信二维码管理
![嘟嘟Pay监控 服务器端 微信二维码管理.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xky1kptj31h10prwg0.jpg)
###### 6. 嘟嘟Pay监控 服务器端 支付宝二维码添加
![嘟嘟Pay监控 服务器端 支付宝二维码添加.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xlxk1lnj31gn0phjrp.jpg)
###### 7. 嘟嘟Pay监控 服务器端 支付宝二维码管理
![嘟嘟Pay监控 服务器端 支付宝二维码管理.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xr19pywj31gv0prjtd.jpg)
###### 8. 嘟嘟Pay监控 服务器端 订单列表
![嘟嘟Pay监控 服务器端 订单列表.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xperq6vj31gr0pkmyy.jpg)


### 三、搭建

#### 1. 下载和上传dudupay_server.war包
下载发送给你的服务器端war包，并上传到服务器上
#### 2. 安装java的运行环境（JDK>=1.8）
下面以ubuntu 18.04为例，
下载oracle jdk11，链接：https://www.oracle.com/java/technologies/javase-jdk11-downloads.html。下载文件jdk-11.0.8_linux-x64_bin.tar.gz
- 创建目录
```bash
sudo mkdir /usr/lib/jvm
```
- 解压缩到该目录
```bash
sudo tar -zxvf jdk-11.0.8_linux-x64_bin.tar.gz -C /usr/lib/jvm
```
- 修改环境变量
```bash
sudo vim ~/.bashrc
```
- 在文件末尾追加下面内容
```env
#set oracle jdk environment
export JAVA_HOME=/usr/lib/jvm/jdk-11.0.8  ## 这里要注意目录要换成自己解压的jdk 目录
export JRE_HOME=${JAVA_HOME}/jre  
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
export PATH=${JAVA_HOME}/bin:$PATH  
```
- 生效环境变量
```bash
source ~/.bashrc
```
- 注册jdk
```bash
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-11.0.8/bin/java 300
```
- 查看java 是否安装成功
```bash
java -version
```
#### 3. 启动服务
- 在war包的同级目录，在控制台输入启动命令 java -jar dudupay_server.war
#### 4. 修改配置
##### （1） 系统设置
- 打开浏览器，访问 localhost:9091
- 默认管理账号为：admin
- 默认通讯密钥为：admin
- 点击系统设置，进入设置页面，修改系统的默认配置
- 修改后台账号和密码  
- 设置订单有效期 这个默认是5分钟，不要修改
- 设置回调地址
    ```
    比如你购买的域名是`niceshop.com`，在系统配置中设置回调地址。
    异步回调:http://niceshop.com/payNotify
    同步回调:http://niceshop.com/payReturn
    如果你开启了https，就把http替换成https
    ```
- 通讯密钥  默认即可，不要修改
- 是否使用ORC， 这个是用来自动识别收款码金额的，方便批量上传收款码。使用的是[百度ORC](https://ai.baidu.com/tech/ocr)。按照提示一步步注册即可。然后创建一个应用得到API Key和Secret Key。
- 区分方式  在同一个时间内，不同的用户购买相同的产品，是根据金额进行区分的。金额增减的步长是0.01元。根据自己情况进行配置
- 微信码、支付宝码 上传不设置具体金额的收款码
######（2）监控端设置
这里只能修改配置数据
![嘟嘟Pay监控 服务器端 监控端设置.png](http://ww1.sinaimg.cn/large/005U6dysly1gj3xgs6jk4j31h40powf1.jpg)
将`/`前面的部分修改成监控 服务器端的域名或者ip:端口。如果没有使用nginx来做代理，端口就是9091。

下面的配置二维码会自动更新，只需要在修改完配置数据后，点击网页的空白部分，就会自动更新二维码。

### 四、搭建和使用教学视频
[搭建和使用视频](https://www.bilibili.com/video/BV1Xi4y177U9?p=1)
