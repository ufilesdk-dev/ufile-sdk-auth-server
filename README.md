  Ufile 签名公钥放在 APP 里实现上传下载签名不安全， 建议用签名服务器，为APP 的上传下载做签名。
  场景一：
    用java sdk 做Andorid APP； 进行用户图片、文件上传功能，需要使用公私钥或者Token 进行签名； 
  
  场景二：
    用 ios sdk 做 IOS APP;  进行用户图片、文件上传功能，需要使用公私钥或者Token 对上传进行签名；

  不安全的做法：APP 里内置 公私钥或者Token，调用上传下载接口实现签名和上传；不安全。 APP 可能会被破解，公私钥、Token 泄露；
  安全的做法： 用户上传前， 把上传的参数，传递给 APP 的服务器，做好签名，返回给APP； APP 用服务器返回的签名，进行上传。
               涉及签名的其他操作类似；
  
  签名服务器代码请参考： https://github.com/ucloud/ufile-sdk-auth-server
