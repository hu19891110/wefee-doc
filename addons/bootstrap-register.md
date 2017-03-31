## 插件启动注册选项

一些较为复杂的插件设计的业务功能非常多，需要预先定一些重复的代码来加快项目的开发和调整项目代码结构，这个时候可能需要在项目运行时就需要注册一些全局方法，常量等行为。所以 `Wefee` 为开发者设计了启动注册功能，具体实现请参考：

#### 第一步

在插件根目录下创建 `bootstrap.php` 文件

#### 第二步

```
<?php
// Your Code.
```

#### 结合 `Composer` 使用：

```
<?php

if (file_exists(__DIR__ . '/vendor/autoload.php')) {
    require_once __DIR__ . '/vendor/autoload.php';
}
```