## 插件主文件

```
<?php
namespace addons\addonsign;

use Qsnh\think\Addons\Addons;

class Addonsign extends Addons
{

    /** 插件安装 */
    public function up()
    {
        //
    }

    /** 插件卸载 */
    public function down()
    {
        //
    }

    /** 插件升级 */
    public function upgrade()
    {
        //
    }

}
```

上面就是插件主文件的结构。

## 注意事项

+ 插件主文件必须继承 `Qsnh\think\Addons\Addons` 。
+ 插件中的三个方法可以为空，但不能没有。


## 常见问题

#### 1、在开发中，插件主文件主要负责数据表的创建与卸载，`Thinkphp5` 中的创建表的方法有：

```
\think\Db::query();
\think\Db::excute();
```

经测试发现，上面的方法每次只能执行一个SQL语句，所以您在开发时候请注意辣！！！

=================================

编辑于：2017年02月23日