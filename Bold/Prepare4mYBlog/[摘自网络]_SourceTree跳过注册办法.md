# SourceTree跳过注册办法

*如题，账户注册会被q，所以如果你此时由于种种情况不能fq，可用此方法*

1. 首先点击安装包安装，到第二步注册账号时，退出程序；
2. 进入电脑文件夹：`C:\Users\{ReolCharm}\AppData\Local\Atlassian\SourceTree` 
3. 新建文件：`accounts.json` 
4. 记事本打开改文件，添加以下代码：

```json
[
  {
    "$id" : "1",
    "$type" : "SourceTree.Api.Host.Identity.Model.IdentityAccount, SourceTree.Api.Host.Identity",
    "Authenticate" : true,
    "HostInstance" : {
      "$id" : "2",
      "$type" : "SourceTree.Host.Atlassianaccount.AtlassianAccountInstance, SourceTree.Host.AtlassianAccount",
      "Host" : {
        "$id" : "3",
        "$type" : "SourceTree.Host.Atlassianaccount.AtlassianAccountHost, SourceTree.Host.AtlassianAccount",
        "Id" : "atlassian account"
      },
      "BaseUrl" : "https://id.atlassian.com/"
    },
    "Credentials" : {
      "$id" : "4",
      "$type" : "SourceTree.Model.BasicAuthCredentials, SourceTree.Api.Account",
      "Username" : "",
      "Email" : null
      },
      IsDefault : false
  }
]
```

5. 保存退出。

 此时再点击安装文件，就直接跳过账号验证部分了。

 

 

 

 

 