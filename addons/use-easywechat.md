## 使用微信组件包

`Wefee` 使用的微信组件包是 `@安正超` 编写的 [https://easywechat.org/](https://easywechat.org/) 。

组件包的具体使用方法请访问上看的链接查看文档。

## 获取 `EasyWechat` 实例

`Wefee` 提供了一个全局注册树让你无需初始化 `EasyWechat` 直接使用：

```
use app\wefee\Tree;

//...

$easywechat = Tree::wechat();

```

## 初始化DIY

> 当然您也可以自己初始化这个包，具体方法请查看文档。


