# 小火箭 Shadowrocket 解锁 Tiktok 免拔卡方法
## 准备工作
- 1、下载Tiktok V21.1.0 版本
- 2、准备美区Apple ID账号
- 3、下载小火箭Shadowrocket
- 4、准备好代理节点

## 一、下载 Tiktok V21.1.0 版本

### APP版本ID查询：https://tools.lancely.tech/apple/app-search?country=us&query=tiktok

- TikTok版本号：21.1.0       版本ID：844024073

- TikTok版本号：21.1.0        版本ID：843972181

### 抓包工具下载地址：

Fiddler下载链接：
https://pc.qq.com/detail/10/detail_3330.html

iTunes2018版下载：https://secure-appldnld.apple.com/itunes12/091-87819-20180912-69177170-B085-11E8-B6AB-C1D03409AD2A6/iTunes64Setup.exe

爱思助手官网：https://www.i4.cn/

爱思助手下载：https://url.i4.cn/faIfqyaa

### Fiddler抓包指令：

        bpu MZBuy.woa


## 二、下载小火箭Shadowrocket
登录自己的美区Apple ID账号，下载小火箭Shadowrocket。

### (一) 配置并安装信任证书
- 1、在【Shadowrocket】配置中找到默认配置文件 <code>default.conf</code>，点击后选择“编辑配置”，然后点击“ https 解密”，接着点击开启开关，接着点击“生成新的CA证书”，接着弹窗确认“生成新的CA证书”，接着点击“安装证书”，接着点击弹窗“允许”，接着选取设备“iPhone”（注：可能没这一步），然后点击弹窗“关闭”。

- 2、在iPhone设置中进入“通用”，然后找到“描述文件与设备管理”，然后点击描述文件“Shadowrocket”，接着点击右上角“安装”，接着输入密码，然后继续点击“安装”，安装成功后会提示已验证。

- 3、继续在通用设置中，找到“关于本机”，然后在最下面找到“证书信任设置”，接着打开“Shadowrocket”证书开关。

### (二) 配置 Tiktok 代码

找到 <code>[URL Rewrite]</code> 字段，复制并粘贴Tiktok 重写规则， <code>URL Rewrite</code> 代码：

        [URL Rewrite]
        (?<=_region=)CN(?=&) JP 307
        (?<=&mcc_mnc=)4 2 307
        ^(https?:\/\/(tnc|dm)[\w-]+\.\w+\.com\/.+)(\?)(.+) $1$3 302
        (^https?:\/\/*\.\w{4}okv.com\/.+&.+)(\d{2}\.3\.\d)(.+) $118.0$3 302

        [MITM]
        hostname = *.tiktokv.com,*.byteoversea.com,*.tik-tokapi.com
    

## 三、启用节点并启动TikTok
- 首先，给小火箭Shadowrocket添加事先准备好的代理URL链接，开启代理节点FQ【注意：香港节点不可用】。

- 然后，打开下载好的TikTok。即可愉快使用啦！

## 四、常见问题
### 1、Tiktok 黑屏仍然无法正常使用
首先，确认 Tiktok 是否按视频操作步骤安装V21.1.0版本；

其次，确认证书是否安装并信任启用，Https解密（MiMt）与重写（Rewrite）是否启用等教程中的内容配置正确；

最后，如没有解决黑屏，卸载TikTok后再次重装后打开。

### 2、Tiktok 换区方法
将 <code>[URL Rewrite]</code> 代码中的JP，更换成你想要的地区简称即可。例如：JP（日本）、KR（韩国）、UK（英国）、US（美国）、TW（台湾）
