# HTTP请求

## `GET` 请求

函数：

```
$res = wefee_get($url, $data = [], $safe = false);
```

参数 | 解释 | 默认
--- | --- | ---
$url | 请求地址 | 无
$data | 请求参数 | 空
$safe | SSL验证 | 否

#### 如果 `URL` `query` 参数过多，可以在  `$data` 里面这样设置：

```
$data = [
    'query' => [
        'query1' => 1,
        'query2' => 2,
        //...
    ],
];
```


## `POST` 请求

函数：

```
$res = wefee_post($url, $data = [], $safe = false);
```

> 参数解释同上。


#### 1、怎么上传文件？

您可以在 `$data` 中这样设置：

```
$data = [
    'body' => $value,
];
```

其中 `$value` 可以是下面的值：

+ `fopen` 返回的资源值：

```
[
    'body' => fopen('/path/to/file', 'r'),
]
```

+ `Psr\Http\Message\StreamInterface` 返回的值：

```
[
    'body' => \GuzzleHttp\Psr7\stream_for('Hello Wefee!');
]
```

#### 2、怎么 `POST` 表单参数？

```
$data = [
    'form_params' => [
        'field1' => $value1,
        'field2' => $value2,
        //...
    ],
];
```

#### 3、怎么上传 `JSON` ？

```
$data = [
    'json' => [
        'josn1' => $value1,
        'json2' => $value2,
        //...
    ],
];
```

#### 4、怎么上传文件 ？

```
$data = [
    `multipart` => [
        'file1' => fopen('/path/to/file', 'r'),
    ],
];
```


## 自定义请求

如果您想 `PUT`, `DELETE`, `PATCH` 等，那么可以使用下面的方法。

```
$res = wefee_request($method, $url, $data = [], $safe = false);
```

> 不需要解释吧！(^ - ^)


## 要求无法满足？

你可以直接使用 `\GuzzleHttp\Client` 。

具体用法请参考：[http://docs.guzzlephp.org/en/latest/quickstart.html#making-a-request](http://docs.guzzlephp.org/en/latest/quickstart.html#making-a-request)