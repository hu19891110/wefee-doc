## 插件配置

#### 创建配置文件

在插件目录下创建 `config.html` 文件。

```
{extend name="./layout/base" /}

{block name="body"}

{include file="./common/nav"}

<div class="container mt-20 bg-fff br-5 pt-15-pb-15">
    <div class="row">
        <div class="col-lg-12">
            <a href="{:url('addons/addons/getList')}">&lt;返回列表</a>
        </div>

        <div class="col-lg-12">
            <form action="{:url('addons/addons/postConfig')}" method="post">
                
                <input type="hidden" name="addons_sign" value="{$addons.addons_sign}">
                {:token()}

            </form>
        </div>
    </div>
</div>

{include file="./common/footer"}

{/block}
```


以上配置文件模板是引用 `wefee` 自带的模板布局，您也可以自己定义。

#### 可能您也注意到了，模板文件有几以下点必须配置：

+ 表单提交地址：`{:url('addons/addons/postConfig')}` 。
+ `{:token}` 的提交
+ `<input type="hidden" name="addons_sign" value="{$addons.addons_sign}">` 插件标识符提交。


## 如何在插件中获取配置？

```
$array = get_addon_config($addonsign);
```
