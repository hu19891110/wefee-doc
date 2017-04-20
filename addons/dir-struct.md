一个标准插件的目录结构：

## 插件目录结构

```
Addonsign    插件标识
┣━controller        Controller目录（可选）
┣━model             Model目录（可选）
┣━hook              钩子存放目录（可选）
┃ ┣━model           程序钩子目录
┃ ┃ ┣━Hook.php      程序钩子文件
┃ ┣━view            视图钩子目录
┃ ┃ ┣━Hook.php      视图钩子文件
┣━public            公共资源目录（可选）
┃ ┣━assets          Application前端资源文件
┣━icon.png          插件Logo,支持png,jpg,gif
┣━Addonsign.php     插件主文件，负责安装，卸载，升级
┣━wefee.html        插件的主界面（可选）
┣━config.html       插件的配置文件（可选）
┣━wefee.json        插件信息
```


## 注意事项

+ 插件目录名格式：插件标识 + 字母小写。
+ 插件主文件名格式：插件标识 + 首字母大写 + 其他字母小写。

#### 公共资源目录是用来干嘛的？

答：公共资源目录是本插件前端所依赖的文件，比如：Jquery等。由于 `Thinkphp5` 是无法直接访问插件目录的，所以在插件安装的时候，系统会将 `./public/assets` 目录下的资源复制一份到 `/root/public/adddons/assets/addonsign/` 目录下面，您的插件在需要该资源的时候直接 `/addons/assets/addonsign/` + `原来目录` 便可以直接访问啦。
