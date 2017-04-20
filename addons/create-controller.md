## 创建一个控制器

#### 问：怎么在插件中创建控制器实现自己的业务逻辑呢？

答：首先，你需要在插件目录下创建 `controller` 目录，目录创建完毕，就可以创建控制器了。创建控制器的规则与 `Thinphp5` 创建控制器的规则一样。文件名首字母大写，后面不需要跟上 `Controller` 等的后缀。

```
<?php namespace addons\addonsign\controller;

use think\Controller;

class Index extend Controller {
    
    public function index()
    {

    }

    //...
}
```

上面是一个标准的插件控制器，是不是和 `Thinkphp5` 一样啊，就这么简单。


#### 怎么实现控制器的权限控制？

一、不做权限控制？

```
class Index extend \think\Controller
{

}
```

二、需要 `wefee` 自带的权限控制？

```
use app\common\controller\Base;

//...

class Index extend Base 
{
    //...
}
```


该继承默认对所有的 `method` 进行权限判断，如果你想自定义，请参考：

```
<?php app\common\controller;

class Base {
    
    protected $loginOnly = [];

    protected $loginExcept = [];

}
```

1、可以将需要权限判断的 `method` 填入 `$loginOnly` 中。

2、获取将不需要权限判断的 `method` 填入 `$loginExcept` 中，是不是很方便？ ^ - ^ 。