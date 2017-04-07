## 创建一个 `Model` 钩子

```
<?php namespace addons\addonsign\hook\model;

class Hook
{

    protected $sign = 'addonsign';

    /**
     * 订阅微信事件
     */
    public function wefeeProcessEvent($params)
    {
        //...
    }

}
```

> 如果创建 `View` 钩子只需将 `model` 换成 `view` 即可。

## 注意事项

+ 文件名与类名必须为：`Hook`。
+ `Hook.php` 文件不需要继承任何其他文件，如果您有需要也可以自定义。
+ `Hook.php` 文件中的方法名都是以钩子命名的，格式：首字母小写的驼峰法。




编辑于：2017年02月23日
