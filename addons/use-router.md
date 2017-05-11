## 使用TP5的路由

首先，您需要在插件中实现一个钩子 `app-init`

```
class Hook
{

    public function appInit()
    {
        /** 简单的示例 */
        \think\Route::get('demo', '\your\controller\file\path@method');
    }

}
```

