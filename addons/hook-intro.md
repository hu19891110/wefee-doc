## `Wefee` 预先定义钩子说明

## 框架系统钩子

#### `app-init`

解释：应用初始化钩子。

#### `app-begin`

解释：应用开始钩子。

#### `module-init`

解释：模块初始化钩子。

#### `action-begin`

解释：控制器初始化钩子。

#### `view-filter`

解释：视图过滤钩子。

#### `app-end`

解释：应用结束钩子。

#### `log-write`

解释：日志写入钩子。

#### `response-end`

解释：输出结束钩子。

## `Wefee` 系统钩子

#### `before-login`

解释：`Wefee` 系统登录之前钩子。

#### `after-login`

解释：`Wefee` 系统登录之后钩子。

## 微信订阅钩子

#### `wefee-subscribe-event`

解释：微信订阅事件钩子。

#### `wefee-subscribe-text`

解释：文本消息订阅钩子。

#### `wefee-subscribe-image`

解释：图片消息订阅钩子。

#### `wefee-subscribe-voice`

解释：音频消息订阅钩子。

#### `wefee-subscribe-video`

解释：视频消息订阅钩子。

#### `wefee-subscribe-location`

解释：位置消息订阅钩子。

#### `wefee-subscribe-link`

解释：链接消息订阅钩子。

#### `wefee-subscribe-original`

解释：原始消息（未经处理的）消息订阅钩子，包括上面所有消息。

## 微信消息处理钩子

#### `wefee-process-event`

解释：微信消息处理钩子（包括：订阅，取消订阅，扫描二维码等）。

#### `wefee-process-image`

解释：图片消息处理钩子。

#### `wefee-process-voice`

解释：音频消息处理钩子。

#### `wefee-process-video`

解释：视频消息处理钩子。

#### `wefee-process-location`

解释：位置消息处理钩子。

#### `wefee-process-link`

解释：链接消息处理钩子。

#### `wefee-process-original`

解释：原始消息处理钩子。

## 微信钩子的参数  `$params` 结构

请求消息基本属性\(以下所有消息都有的基本属性\)：

```
$message->ToUserName    接收方帐号（该公众号 ID）
$message->FromUserName  发送方帐号（OpenID, 代表用户的唯一标识）
$message->CreateTime    消息创建时间（时间戳）
$message->MsgId         消息 ID（64位整型）
```

##### 文本：

```
$message->MsgType  text
$message->Content  文本消息内容
```

##### 图片：

```
$message->MsgType  image
$message->PicUrl   图片链接
```

##### 语音：

```
$message->MsgType        voice
$message->MediaId        语音消息媒体id，可以调用多媒体文件下载接口拉取数据。
$message->Format         语音格式，如 amr，speex 等
$message->Recognition * 开通语音识别后才有
```

> 请注意，开通语音识别后，用户每次发送语音给公众号时，微信会在推送的语音消息XML数据包中，增加一个 `Recongnition` 字段

##### 视频：

```
$message->MsgType       video
$message->MediaId       视频消息媒体id，可以调用多媒体文件下载接口拉取数据。
$message->ThumbMediaId  视频消息缩略图的媒体id，可以调用多媒体文件下载接口拉取数据。
```

##### 小视频：

```
$message->MsgType     shortvideo
$message->MediaId     视频消息媒体id，可以调用多媒体文件下载接口拉取数据。
$message->ThumbMediaId    视频消息缩略图的媒体id，可以调用多媒体文件下载接口拉取数据。
```

##### 事件：

```
$message->MsgType     event
$message->Event       事件类型 （如：subscribe(订阅)、unsubscribe(取消订阅) ...， CLICK 等）
```

##### 扫描带参数二维码事件

```
$message->EventKey    事件KEY值，比如：qrscene_123123，qrscene_为前缀，后面为二维码的参数值
$message->Ticket      二维码的 ticket，可用来换取二维码图片
```

##### 上报地理位置事件

```
$message->Latitude    23.137466   地理位置纬度
$message->Longitude   113.352425  地理位置经度
$message->Precision   119.385040  地理位置精度
```

##### 自定义菜单事件

```
$message->EventKey    事件KEY值，与自定义菜单接口中KEY值对应，如：CUSTOM_KEY_001, www.qq.com
```

##### 地理位置：

```
$message->MsgType     location
$message->Location_X  地理位置纬度
$message->Location_Y  地理位置经度
$message->Scale       地图缩放大小
$message->Label       地理位置信息
```

##### 链接：

```
$message->MsgType      link
$message->Title        消息标题
$message->Description  消息描述
$message->Url          消息链接
```

具体请参开：[https://easywechat.org/zh-cn/docs/server.html](https://easywechat.org/zh-cn/docs/server.html)

#### 钩子怎么使用？

首先你需要在插件目录下创建一个文件，它的目录是： `hook/model/Hook.php`。

```
<?php namespace addons\插件标识\hook\model;

class Hook
{
    //...
}
```

上面是它的结构。这是时候如果你想使用 `wefee-subscribe-text` 钩子的话，你可以这样做：

```
<?php namespace addons\插件标识\hook\model;

class Hook
{

    public function wefeeSubscribeText($params)
    {
        //...业务逻辑
    }

}
```

怎么样？非常简单吧！

> 注意，钩子方法随便的 return 数据。因为这会导致其他后续插件无法执行。

如果没有必要请不要随便你使用 `return` 语句，或者你可以这样使用：

```
return ; 
```



编辑于：2017年02月27日

