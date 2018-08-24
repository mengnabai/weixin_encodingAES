# weixin_encodingAES
微信公众号开发，消息加解密，python3版本

微信公众号的消息加密方式有以下三种：
- 明文模式：维持现有模式，没有适配加解密新特性，消息体明文收发，默认设置为明文模式
- 兼容模式：公众平台发送消息内容将同时包括明文和密文，消息包长度增加到原来的3倍左右；公众号回复明文或密文均可，不影响现有消息收发；开发者可在此模式下进行调试
- 安全模式（推荐）：公众平台发送消息体的内容只含有密文，公众账号回复的消息体也为密文，建议开发者在调试成功后使用此模式收发消息

参考[微信公众平台-消息加解密说明](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1434696670)中的示例代码，使用安全模式对公众号的消息进行加解密，由于示例中的python代码是python2写的，而我们自己是用python3进行开发的，所以需要对示例代码进行修改以适配python3。

主要差别在于字符的类型，最好将所有str类型的文本或者字段转成bytes类型。
