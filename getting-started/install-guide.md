（如果安装错误，请下载最新安装包！）

### 环境要求

* PHP版本 &gt;= 5.6。
* openssl 扩展。
* rewrite 扩展。
* fileinfo 扩展。

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

```
composer install
```

> 注意，配置到这里其实已经可以直接访问URL进行安装了。

三、配置数据库信息：

```
cp .env.example .env
vi .env
```

四、安装数据库：

```
php think migrate:run

php think seed:run
```

五、配置 Apache 目录：

我当前的 `wefee` 程序是 `/var/www/html/wefee` 这个目录，那么我的 `Apache` 的配置目录是 `/var/www/html/wefee/public` 。（谨记！否则会出现样式文件无法加载的情况。）

六、登录后台：

> 注意，这时你需要手动的创建一个安装锁文件：`data/install/install.lock` ，文件内容随意。

```
sudo vi ./data/install/install.lock
```


地址：`http://domain.com/admin`  
账号：`admin`  
密码：`ilovewefee`


### 权限问题

> 建议：最好给予 `wefee` 整个目录0777权限.


### 伪静态配置

Nginx:  
```
location / {
    try_files $uri $uri/ /index.php?s=$uri&$args;
}
```
