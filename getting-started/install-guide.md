### 环境要求

* PHP版本 &gt;= 5.5.9。
* openssl 扩展。
* rewrite 扩展。
* fileinfo 扩展。
* 命令行可以运行 php ，如：php -v

### 开始安装

一、下载程序：

Github源（国外，较慢）

```
git clone https://github.com/Wefee/Wefee.git
```

Coding源（较快）

```
git clone https://git.coding.net/wefee/wefee.git
```

OsChina（较快）

```
git clone https://git.oschina.net/wefee/Wefee.git
```

二、安装依赖：

> 进入 wefee 安装目录，在命令号输入下面命令

```
php composer.phar install
```

三、配置数据库信息：

```
cp .env.example .env
vi .env
```

> 或者您可以手动复制 .env.example 文件重命名为 .env ，打开 .env 文件修改里面的数据库信息。

四、安装数据库：

```
php think migrate:run

php think seed:run
```

五、配置 Apache 目录：

我当前的 `wefee` 程序是 `/var/www/html/wefee` 这个目录，那么我的 `Apache` 的配置目录是 `/var/www/html/wefee/public` 。（谨记！否则会出现样式文件无法加载的情况。）

六、登录后台：

地址：`http://domain.com/admin`  
账号：`admin`  
密码：`ilovewefee`

安装过程到此结束。^ - ^。





======================================================



编辑于：2017年02月23日

