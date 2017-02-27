## 控制器，视图都创建好了，那么怎么生成URL去访问呢？

`Wefee` 提供了一个函数去生成插件中 `Controller` 的访问URL：

```
string $url = aurl('插件标识/控制器名/方法名', [GET参数]);
```


控制器名默认： `index` 。
方法名默认： `index` 。

#### 怎么获取参数？

```
$request = request();

var_dump($request->param());
```


======================================

 编于：2017年02月27日