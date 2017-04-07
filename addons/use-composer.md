## 使用 `Composer`

使用 `Composer` 安装包之后会生成 `vendor` 目录，其目结构如下：

```
vendor
|--autoload.php
|--otherfile.php
```

#### 在 `bootstrap.php` 文件中注册：

关于 `bootstrap.php` 文件的说明请参考：[启动注册](bootstrap-register.md)。

```
<?php

if (file_exists(__DIR__ . '/vendor/autoload.php')) {
    require_once __DIR__ . '/vendor/autoload.php';
}

//...
```


#### 注意事项

`Wefee` 已经在默认加载了下面的包，请不要在插件中重复install：

+ qsnh/think-auth
+ overtrue/wechat
+ qsnh/think-addons
+ qsnh/think-repository
+ phootwork/file
+ qsnh/think-upload
+ topthink/think-queue
+ guzzlehttp/guzzle
+ topthink/think-image
+ topthink/think-captcha
+ anekdotes/file
