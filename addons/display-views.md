## 渲染视图

#### 一、创建视图

在插件目录下定义 `views` 目录，接着就可以在该目录下定义驶入文件了！

#### 二、在 `Controller` 中渲染。

```
return view(VIEW_PATH . '/index/index.html');
```

插件中的视图渲染需要手动的指明视图所在的绝对路径，好在 `wefee` 已经预先定义了 `VIEW_PATH` 常量，它直接指向当前插件目录下的 `views` 目录中。