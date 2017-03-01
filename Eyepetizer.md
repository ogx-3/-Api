# 开眼 #

- [首页](#home)

<h2 id="home">首页</h2>

url：[`http://baobab.kaiyanapp.com/api/v4/tabs/selected`](http://baobab.kaiyanapp.com/api/v4/tabs/selected)

拼接参数：

- `udid`：用户唯一标识。该参数可为空也可去除
- `vc`：???，固定值`168`。该参数可为空也可去除
- `vn`：客户端版本。该参数可为空也可去除
- `deviceModel`：手机信息。该参数可为空也可去除
- `first_channel`：???，固定值 `eyepetizer_baidu_market`。该参数可为空也可去除
- `last_channel`：???，固定值 `eyepetizer_baidu_market`。该参数可为空也可去除
- `system_version_code`：手机系统版本。该参数可为空也可去除

url 示例：[`http://baobab.kaiyanapp.com/api/v4/tabs/selected?udid=11111&vc=168&vn=3.3.1&deviceModel=Huawei%36&first_channel=eyepetizer_baidu_market&last_channel=eyepetizer_baidu_market&system_version_code=20`](http://baobab.kaiyanapp.com/api/v4/tabs/selected?udid=11111&vc=168&vn=3.3.1&deviceModel=Huawei%36&first_channel=eyepetizer_baidu_market&last_channel=eyepetizer_baidu_market&system_version_code=20) 或 [`http://baobab.kaiyanapp.com/api/v4/tabs/selected`](http://baobab.kaiyanapp.com/api/v4/tabs/selected)

json 示例：


解析：
`itemList` 内容可根据 `type` 和 `dataType` 分成5种类型

<h3 id="home_video">视频</h3>
- `type`：类型，固定值 `video`
- `data`：具体数据
	- `dataType`：数据类型，固定值 `VideoBeanForClient`
	- `id`：视频 id
	- `title`：标题
	- `description`：简易描述
	- `provider`：内容提供商信息
	- `category`：分类
	- `author`：作者
	- `cover`：背景图信息
	- `playUrl`：视频播放地址
	- `duration`：播放时长
	- `webUrl`：网页链接
	- `playInfo`：视频的几种播放选择
		- `height`：视频高度
		- `width`：视频宽度
		- `urlList`：播放链接
		- `name`：视频清晰度
	- `consumption`
		- `collectionCount`：多少人喜欢
		- `shareCount`：多少人收藏
		- `replyCount`：多少人回复
	- `tags`：视频标签
		- `id`：分类的 id
		- `name`：分类的名称
		- `actionUrl`：分类的 url

<h3 id="home_textFooter">textFooter</h3>
- `type`：类型，固定值 `textFooter`
- `data`：具体数据
	- `text`：信息
	- `actionUrl`：需要拼接的 url

<h3 id="home_videoCollectionWithCover">videoCollectionWithCover</h3>
- `type`：类型，固定值 `videoCollectionWithCover`
- `data`：具体数据
	- `dataType`：数据类型，取值 `ItemCollection`
	- `header`：内容
		- `id`：
		- `font`：字体信息
		- `cover`：背景图信息
		- `actionUrl`：需要拼接的 url
	- `itemList`
		- // 等同[视频](#home_video)
	- `count`：`itemList` 长度，即返回数据的总长度

<h3 id="home_textHeader">textHeader</h3>
同[textFooter](#home_textFooter)

<h3 id="home_videoCollectionOfFollow">home_videoCollectionOfFollow</h3>
- `type`：类型，固定值 `videoCollectionOfFollow`
- `data`：具体数据
	- `dataType`：数据类型，取值 `ItemCollection`
		- `header`：内容
			- `id`：
			- `title`：标题
			- `font`：字体信息
			- `cover`：背景图信息
			- `iconList`：嵌入的小图 url
			- `actionUrl`：需要拼接的 url
			- `description`：简易描述
		- `itemList`
			- // 等同[视频](#home_video)
		- `count`：`itemList` 长度，即返回数据的总长度
- `count`：`itemList` 长度，即返回数据的总长度
- `nextPageUrl`：加载下一页的 url
- `date`：日期
- `nextPublishTime`：下次更新日期
- ``：
- ``：