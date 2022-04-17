# iCloud 安全能力分析

## 目标

分析iCloud产品安全能力、安全技术，提出其中可参考的功能，用于OPPO安全能力提升。

分析思路：

1. Apple官方提出的安全能力总体了解

2. iCloud 产品安全相关功能整理

3. 开发文档中iCloud安全相关开发能力整理

4. 第三方对iCloud安全的分析



## Apple官方文档描述的安全能力

[安全性概览 - Apple Developer](https://developer.apple.com/cn/security/)

1. 账号登陆（使用什么协议？可能与icloud关系不太大）

2. 建立安全链接（特殊的是DeviceCheck和信任证书），虽然icloud有使用，但应该没有icloud特有的能力

3. 用途字符串：借助用途字符串，您可以静态地声明 App 所使用的敏感数据和资源。

4. iCloud 钥匙串 ： 重点分析

5. 加解密接口/APi： icloud肯定有使用，但是否有特殊的地方？



[iCloud 安全性概览](https://support.apple.com/zh-cn/HT202303)

1. 主要是加密，各种服务同步的加密类型

2. iCloud数据恢复的安全

3. 健康数据备份加密



## icloud 产品安全相关功能

1. 各种功能的云同步
   
   <img src="iCloud%20安全能力分析.assets/2022-04-17-16-27-38-image.png" title="" alt="" width="336">

2. 隐藏邮件地址
   
   <img src="iCloud%20安全能力分析.assets/2022-04-17-16-28-09-image.png" title="" alt="" width="330">

3. 找到我功能（在app内通过apple id找人？）
   
   <img title="" src="iCloud%20安全能力分析.assets/2022-04-17-16-29-18-image.png" alt="" width="331">

4. 家人共享相册中的安全性
   
   <img src="iCloud%20安全能力分析.assets/2022-04-17-16-30-13-image.png" title="" alt="" width="326">



## 开发文档中iCloud安全相关开发能力整理

1. cloudkit 库，包含加密数据功能。 [CloudKit - iCloud - Apple Developer](https://developer.apple.com/icloud/cloudkit/), [Encrypt_user_data](https://developer.apple.com/documentation/cloudkit/encrypting_user_data/)

2. icloud log 对用户隐私的处理：[Logs - iCloud - Apple Developer](https://developer.apple.com/icloud/logs/)

   3. Telemetry 指标统计工具对用户隐私的处理： [Telemetry - iCloud - Apple Developer](https://developer.apple.com/icloud/telemetry/)

4. iCloud Keychain verification codes. [Secure login with iCloud Keychain verification codes - WWDC21 - Videos - Apple Developer](https://developer.apple.com/videos/play/wwdc2021/10105/)

5. Keychain : [keychain_services](https://developer.apple.com/documentation/security/keychain_services/)



## 第三方对iCloud安全的分析

1. iCloud数据安全分析： [苹果 iCloud 进入国内就不安全了吗？从密码学算法与应用安全谈 iCloud - 少数派](https://sspai.com/post/26497)

2. [访问iCloud的安全性问题的深入探讨 - FreeBuf网络安全行业门户](https://www.freebuf.com/articles/database/210446.html)

3. 
