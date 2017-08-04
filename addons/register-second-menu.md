### 注册二级菜单

二级快捷菜单主要是给插件使用的，方便管理员快捷的访问经常使用的插件。`Wefee` 在系统启动之初就预先注册了 `config('WEFEE_SECOND_MENUS')` 配置，如果我们想要注册二级菜单，非常的简单，请看下面教程：

#### 第一步，我们需要注册一个钩子

在 `hook/model/Hook.php` 文件下注册一个方法：

```
public function appBegin(&$param)
{
    $needRegisterMenu = [
        ['title' => '百度', 'href' => 'https://www.baidu.com/'],
        ['title' => 'Google', 'href' => 'https://www.google.com/'],
    ];

    $needRegisterMenu = array_merge(config('WEFEE_SECOND_MENUS'), $needRegisterMenu);
    config(['WEFEE_SECOND_MENUS' => $needRegisterMenu]);
}
```


就这么多，很简单吧！ ^ - ^ !