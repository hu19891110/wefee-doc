## 控制器，视图都创建好了，那么怎么生成URL去访问呢？

`Wefee` 提供了一个函数去生成插件中 `Controller` 的访问URL：

```
string $url = aurl('插件标识/控制器名/方法名', [GET参数]);
```


控制器名默认： `index` 。
方法名默认： `index` 。

#### 注意

如果您定义的控制器存在多级目录，那么请这样写：dir1.dir2.controller。举个例子：

下面是我控制器的目录结构
```
controller
|--admin
|--|--Index.php
|--|--Demo.php
```

那么 `Index.php` 的中的 `index` 方法的URL该怎么写呢？

```
aurl('插件标识/admin.index/index');
```


#### 怎么获取参数？

```
$request = request();

var_dump($request->param());
```
