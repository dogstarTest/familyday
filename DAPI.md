 
**接口调用文档**

Author:  [Linkenpeng](mailto:collin_linken@qq.com)

[前言](#前言)

* 第一部分 [下行接口部分](#下行接口部分)
	* 1．1、	[广告接口](#广告接口)
	* 1．2、	[今日话题](#今日话题)
	* 1．3、	[家庭动态列表接口](#家庭动态列表接口)
	* 1．4、	[照片详情接口](#照片详情接口)
	* 1．5、	[日记详情接口](#日记详情接口)
	* 1．6、	[视频详情接口](#视频详情接口)
	* 1．7、	[活动详情接口](#活动详情接口)
	* 1．8、	[评论列表接口](#评论列表接口)
	* 1．9、	[个人空间接口](#个人空间接口)
	* 1．10、[空间内容列表接口](#空间内容列表接口)
	* 1．11、[对话列表接口](#对话列表接口)
	* 1．12、[对话详情接口](#对话详情接口)
	* 1．13、[通知列表接口](#通知列表接口)
	* 1．14、[更多信息接口](#更多信息接口)
	* 1．15、[用户名片接口](#用户名片接口)
	* 1．16、[家人列表接口](#家人列表接口)
	* 1．17、[搜索家人接口](#搜索家人接口)
	* 1．18、[家人申请接口](#家人申请接口)
	* 1．19、[有奖任务列表接口](#有奖任务列表接口)
	* 1．20、[随机有奖任务提醒](#随机有奖任务提醒)
	* 1．21、[有奖任务详情](#有奖任务详情)

* 第二部分 [上行接口部分](#上行接口部分)
	* 2.1、 [普通登录接口](#普通登录接口)
	* 2.2、	[第三方登录接口](#第三方登录接口)
	* 2.3、	[注册接口](#注册接口)
	* 2.4、	[个人头像和昵称设置接口](#个人头像和昵称设置接口)
	* 2.5、	[孩子信息设置接口](#孩子信息设置接口)
	* 2.6、	[创建空间接口](#创建空间接口)
	* 2.7、	[申请成为家人接口](#申请成为家人接口)
	* 2.8、	[同意成为家人接口](#同意成为家人接口)
	* 2.9、	[收藏动态](#收藏动态)
	* 2.10、	[评论接口](#评论接口)
	* 2.11、	[参加活动接口](#参加活动接口)
	* 2.12、	[表态接口](#表态接口)
	* 2.13、	[发消息（对话）接口](#发消息（对话）接口)
	* 2.14、	[修改头像接口](#修改头像接口)
	* 2.15、	[修改昵称接口](#修改昵称接口)
	* 2.16、	[修改生日接口](#修改生日接口)
	* 2.17、	[参加有奖任务接口](#参加有奖任务接口)
	* 2.18、	[修改备注关系接口](#修改备注关系接口)
	* 2.19、	[修改生日提醒接口](#修改生日提醒接口)
	* 2.21、	[单张图片上传接口](#单张图片上传接口)
	* 2.22、	[发表照片接口](#发表照片接口)
	* 2.23、	[转发照片接口](#转发照片接口)
	* 2.24、	[发表日记接口](#发表日记接口)
	* 2.26、	[转发日记接口](#转发日记接口)
	* 2.27、	[发表活动接口](#发表活动接口)
	* 2.28、	[转发活动接口](#转发活动接口)
	* 2.29、	[活动分类接口](#活动分类接口)
	* 2.30、	[发表视频接口](#发表视频接口)
	* 2.31、	[转发视频接口](#转发视频接口)
	* 2.32、	[发表我想说接口](#发表我想说接口)
	* 2.33、	[空间名称列表接口](#空间名称列表接口)
	* 2.34、	[和谁在一起的人列表接口](#和谁在一起的人列表接口)

 
<h2>前言</h2>  
	本接口调用文档，旨在告诉客户端如何调用服务器请求，从而实现客户端的所有业务逻辑。  
	下行接口：根据客户端发起的请求，网站服务端进行业务逻辑的操作之后，然后通过接口返回客户端所需要的各种图文数据;  		上行接口：如果客户端所要发起的操作，是需要触发服务端进行系统业务逻辑操作，或者进行数据增删改等操作的时候，   会通过上行接口将客户端的请求，送达给服务器，并在后台进行相应的业务逻辑操作，    最后将获得相应的返回值以及是否操作成功的标记。

注：

	1)	下行接口中，除非标注有POST方式，否则一律用GET方式请求数据。  
	2)	上行接口中，除非标注有GET方式，否则一律用POST方式发送数据。  
	3)	在上行接口中，包含有部分下行接口，用来生成发布界面，如：空间列表，和谁在一起。  

所有的接口服务器均以Json格式返回数据，在每个返回的信息中，分别是：   
>  

	data: 	下行接口中代表客户端真正需要的数据。  
	msgkey: 代表服务器针对该次请求的信息提示key，客户端可以根据此信息自己再定义信息。  
	msg: 	代表服务器针对该次请求的辅助信息提示。  
	error: 	代表是否获取数据错误状态， 1 失败， 0成功。  
	
返回的数据示例：

>  

	{

		"data": {
			"adid": "2",
			"title": "手机广告",
			"imagesrc": "http://www.baidu.com/img/baidu_sylogo1.gif",
			"idtype": "blog",
			"id": "1"
		},
		"msgkey": "rest_success",
		"msg": "数据获取成功",
		"error": 0
	}


注：开发的时候如果想方便的查看每个接口的返回信息，可以在url中增加一个debug=1的参数，如：
网站域名/dapi/info.php?ac=ad&debug=1
若没有此参数，将返回json数据格式。


<h2>第一部分</h2> <h2>下行接口部分</h2>

<h3>1.1、</h3><h3>广告接口</h3>  
【参数】  
无  
【调用方式】  
网站域名/dapi/info.php?ac=ad  
【返回值】  
> 

	title		广告标题  
	imagesrc	广告图片url  
	idtype		广告对应的帖子类型  
	id			帖子id

 
<h3>1.2、</h3><h3>今日话题</h3>  
【参数】  
无
【调用方式】  
网站域名/dapi/space.php?do=topic  
【返回值】  
>  

	subject:			标题
	message:			内容
	dateline:			发布时间
	endtime：			结束时间


 
<h3>1．3、	</h3><h3>家庭动态列表接口</h3>  
【参数】  
>  

	do:	 	home
	uid:		用户id
	perpage: 分页大小， 默认10
	page:	当前页
【调用方式】  
网站域名/dapi/space.php?do=home&uid=1  
【返回值】  

>

	1）多维数组：  
		avatar: 		发布用户头像url
		name: 			用户昵称
		note : 			关系备注
		dateline: 		动态时间
		id: 			动态id
		idtype: 		动态类型(
				eventid: 		发布活动
				reeventid：		转采活动
				eventcomment：	活动评论
				blogid: 	 	发布更新日志
				reblogid： 		转采日志
				blogcomment： 	日志评论
				photoid：	  	上传图片
				photocomment： 	评论图片
				rephotoid：		转采图片
				videoid：		发布视频
				revideoid：		转采视频
				videocomment：	视频评论
				profield: 		更新资料
				avatar:  		更新头像
		)
	2）转采  
		fuid				原作者uid
		fname				原作者名称
	3)普通动态  
		title: 				动态标题
		image_1 – image_4:	动态带的图片和内容附图的数量, 如果有图片则有值，否则为空值
		message:			动态简介文字
		id:					原文id
		fuid:				原文所属于的空间id
		fname:				原文所属于的空间名称
	4） 活动动态  
		lng:				活动地点的经度
		lat:				活动地点的纬度
		location:			活动地点的地名
	5） 行为动态  
		uid:				行为人uid
		name:				行为人名字
		fuid:				对象人uid
		fname:				对象人名字
		？？：				被操作的对象名称
		id：				被操作的id
		idtype：			被操作的类型
	6) 发布渠道 
		come: 				发布的渠道  
	
	7） 最新的两条评论  
		comment： 	数组
			authorid：		评论人的uid
			authorname:		评论人的名字
			message：		评论内容
			dateline：		评论时间


 
<h3>1．4、	</h3><h3>照片详情接口</h3>  
【参数】  
> 

	do:	 photo
	uid: 照片拥有人的uid
	id:	照片帖子id
【调用方式】  
网站域名/dapi/space.php?do=photo&uid=1&id=293  
【返回值】  
>  

	1）
	uid:			发布者的uid
	name:			发布者的name
	note:			关系备注
	dateline:		发布时间
	title:			标题
	uid:			空间id
	name:			空间名称
	2）转采
	fuid:			转采uid
	fname:			转采者名字
	3） 
	rephotonum：	转采数量
	replynum：		评论数量
	love:			收藏数量
	4) 正文url
	piclist:		多个图片组合起来的数组
	pic:			图片地址	
	title：			图片标题
	message:		改组照片的描述,正文  =  piclist + message 组合起来显示
	5）
	lng：			经度
	lat：			纬度
	address：		地点名称
	6） 和谁在一起
	together：		多维数组
		uid:		在一起的人的uid
		name:		在一起的人的名字
		avatar:		在一起的人的头像
	7) 评论（表态）
	commentlist:多维数组
		authorid：	评论人uid
		avatar:		评论人头像
		message：	评论内容
	8) 发布渠道 
	come:			发布渠道
 
<h3>1．5、	</h3><h3>日记详情接口</h3>
【参数】  
>  
	
	do:	 blog
	uid:  日志拥有人的uid
	id:	 日志id 
【调用方式】
网站域名/dapi/space.php?do=blog&uid=1&id=18  
【返回值】  
>  
		
	1）
	uid:			发布者的uid
	name:			发布者的name
	note:			关系备注
	dateline:		发布时间
	subject:		标题
	uid:			空间id
	name:			空间名称
	2）转采
	fuid:			转采uid
	fname:			转采者名字
	3） 
	reblognum：		转采数量
	replynum：		评论数量
	love:			收藏数量
	4) 正文url
	message:		正文的内容， html格式的
	5）
	lng：			经度
	lat：			纬度
	address：		地点名称
	6） 和谁在一起
	together：		多维数组
		uid:		在一起的人的uid
		name:		在一起的人的名字
		avatar:		在一起的人的头像
	7) 评论（表态）
	commentlist:多维数组
		authorid：	评论人uid
		avatar:		评论人头像
		message：	评论内容
	8) 发布渠道 
	come:			发布渠道

 
<h3>1．6、	</h3><h3>视频详情接口</h3>
【参数】  
>  
	
	do:	 video
	uid: 视频拥有人的uid
	id:	 视频id  
【调用方式】  
网站域名/dapi/space.php?do=video&uid=1&id=4  
【返回值】  
>  
		
	1）
	uid:			发布者的uid
	name:			发布者的name
	note:			关系备注
	dateline:		发布时间
	subject:		标题
	uid:			空间id
	name:			空间名称
	2）转采
	fuid:			转采uid
	fname:			转采者名字
	3） 
	revideonum：	转采数量
	replynum：		评论数量
	love:			收藏数量
	4) 视频url
	videourl:		视频url
	subject:		视频标题
	5）
	lng：			经度
	lat：			纬度
	address：		地点名称
	6） 和谁在一起
	together：		多维数组
		uid:		在一起的人的uid
		name:		在一起的人的名字
		avatar:		在一起的人的头像
	7) 评论（表态）
	commentlist:多维数组
		authorid：	评论人uid
		avatar:		评论人头像
		message：	评论内容
	8) 发布渠道 
	come:			发布渠道

 
<h3>1．7、	</h3><h3>活动详情接口</h3>  
【参数】  
>  

	do:	 event
	uid:  活动发布人的uid
	id:	 活动id

【调用方式】  
网站域名/dapi/space.php?do=event&uid=1&id=223  
【返回值】  
>  

	1）
	uid:			发布者的uid
	name:			发布者的name
	note:			关系备注
	dateline:		发布时间
	title:			标题
	uid:			空间id
	name:			空间名称
	2）转采
	fuid:			转采uid
	fname:			转采者名字
	3） 
	reeventnum：	转采数量
	replynum：		评论数量
	love:			收藏数量
	4) 活动信息
	title:			活动标题
	detail：		活动主要内容
	dateline:		活动时间
	lng：			经度
	lat：			纬度
	location：		活动地点
	5） 和谁在一起
	together：		多维数组
		uid:		在一起的人的uid
		name:		在一起的人的名字
		avatar:		在一起的人的头像
	6) 评论（表态）
	commentlist:多维数组
		authorid：	评论人uid
		avatar:		评论人头像
		message：	评论内容
	7) 发布渠道 
	come:			发布渠道
	

 
<h3>1．8、	</h3><h3>评论列表接口</h3>  
【参数】  
>  

	do:			comment
	id:			被评论的对象id
	idtype:		被评论的类型(photoid: 照片,  'eventid': 活动,  'blogid'：日志,  'videoid'：视频)
	page:		当前页，默认1
	perpage:	每页数量，默认10

【调用方式】  
网站域名/dapi/space.php?do=comment&id=293&idtype=photoid  
【返回值】  
>  

	authored:		评论用户uid、
	avatar:			头像url
	authorname:		评论用户名
	note:			关系备注
	message:		评论内容
	dateline:		评论时间
	lng:			经度
	lat:			纬度
	address:		地名
	come:			发布来源

<h3>1．9、	</h3><h3>个人空间接口</h3>  
【参数】  
>  
	
	uid:  		自己的uid
	page:		家庭成员的当前页，默认1
	perpage:	家庭成员的分页数, 默认10

【调用方式】  
网站域名/dapi/space.php?uid=1
【返回值】  
>  

	1）
	uid:			用户id
	name:			用户名字
	avatar:			用户头像url
	fmembers:		家人数量
	feeds:			动态数量
	birthday：		生日
	2）家人列表
	fmemberlist：	家人列表数组
		uid:		家人uid
		name:		家人名字
		avatar:		家人头像
		note：		关系备注
	3) 空间列表
	spacelist:		数组
		uid:		空间id
		name:		空间名称
	avatar:	空间头像
		latestpic:	空间最新一张图片
		blogs:		空间日志数
		photos:		空间照片数
		events:		空间活动数
		videos:		空间视频数

 
<h3>1．10、	</h3><h3>空间内容列表接口</h3>  
【参数】  
>  

	uid:			用户id
	tagid:			空间id
	page:			当前页，默认1
	perpage:		每页大小，默认1 (如果是ipad版本，可以传递大点的值过来,比如：20)  
【调用方式】  
网站域名/dapi/space.php?do=familyspace&uid=4&tagid=377  
【返回值】  
>  

	tagname:		标签名，即：网站详情中的概述
	blognum:		该标签的信息数量
	feedlist:		信息详情，【数组】
		image_1		图片地址
		idtype:		信息的类型，包括（'blogid','photoid','eventid','videoid'）
		id:			信息的id
		uid:		该条信息的发布人uid
		subject:	标题
		message:	概述
		comment	 评论内容【数组】
			authoreid	评论人的uid
			author		评论人的名字
			message		评论内容

 
<h3>1．11、	</h3><h3>对话列表接口</h3>  
【参数】  
>  

	uid:		用户id
	page:		当前页, 默认1
	perpage:	分页大小，默认10
【调用方式】  
网站域名/dapi/space.php?do=pm&filter=privatepm&uid=1  
【返回值】  
>  

	data:		数组
		msgfromid:				对话对方用户uid
		msgfromname:			对话对方name
		msgfromavatar:			对方对方的头像url
		note:					备注名
		lastdateline:			最后对话的时间
		lastsummary:			最后对话的内容
		lng:					最后对话纬度
		lat:					最后对话经度
		address;				最后对话地点
		come:					最后对话发布来源
		new:					这个对话中有几个未读消息的数量
 
<h3>1．12、	</h3><h3>对话详情接口</h3>  
【参数】  
>  

	uid:		用户id
	touid: 		对话的用户id
	page:		当前页, 默认1
	perpage:	分页大小，默认10  
【调用方式】  
网站域名/dapi/space.php?do=dialog&uid=1&touid=4  
【返回值】  
>  

	fromuser: 	
		uid:			当前用户的uid
		name:			当前用户的name
		avatar:			头像url
		lastmsgtime:	最后一条对话的时间
	touser: 	
		uid:			对方的uid
		name:			对方的name
		avatar:			对方头像url
	dialog: 多条信息的数组
		msgfromid:		发信人uid
		msgtoid:		接收信息人uid
		message:		信息内容
		dateline:		发信时间
		lng:			经度
		lat:			纬度
		address:		地名
		come:			发布来源


<h3>1．13、	</h3><h3>通知列表接口</h3>  
【参数】  
>  

	uid:			用户id
	page:			当前页, 默认1
	perpage:		分页大小，默认10
【调用方式】  
网站域名/dapi/space.php?do=notice&uid=4  
【返回值】  
>  

	1）	
	authorid:			通知的用户uid
	authouravatar:		头像url
	authourname:		name
	note:				通知详情
	2）	通知详情内如果包含其他用户的话
	fuid:				其他用户uid
	fname:				name
	3）	通知详情内如果包含某个帖子
	fid:				其它帖子的id
	ftitle:				其他帖子的标题
	4）	通知的阅读状况
	new:				0已读, 1未读
 
<h3>1．14、	</h3><h3>更多信息接口</h3>  
【参数】  
>  

	uid:			用户id
【调用方式】  
网站域名/dapi/space.php?do=setup&uid=1  
【返回值】  
>  

	uid:			用户id
	name:			用户名字
	avatar:			用户头像url
	phone:			电话号码
	birthday：		生日
	fmembers:		家人数量
	frequests:		家人申请数量
	credit:			金币
	tasknum:		有奖任务
	lovenum:		收藏数量
	存客户端:		主题
	sina_uid:		是否绑定新浪微博，有uid则说明绑定
	is_qq_bing:		是否绑定qq
 
<h3>1．15、	</h3><h3>用户名片接口</h3>  
【参数】  
>  

	uid:			自己的用户id
	fuid:			对方的用户id  
【调用方式】  
网站域名/dapi/space.php?do=friend&uid=4&fuid=1  
【返回值】  
>  

	uid:			对方的uid
	name:			对方的昵称
	phone:			对方的电话号码
	avatar:			对方的头像
	birthday:		对方生日
	fmembers：		对方的家人数量
	tags:			空间数量
	note：			关系备注
	lastlogin:		最后一次登录时间

 
<h3>1．16、	</h3><h3>家人列表接口</h3>  
【参数】  
>  

	uid:		用户id  
【调用方式】  
网站域名/dapi/space.php?do=fmembers&uid=1  
【返回值】  
>  

	uid:				自己的用户id
	name:				自己的昵称
	avatar:				自己的头像
	fmembers：			自己的家人数量
	fmemberlist：家人列表【数组】
			uid			家人的用户id
		    name		家人的昵称
		    avatar：	家人的头像
		    note:		家人关系备注 
		    feeds:		家人动态数量 
		    fmembers：	家人的家人数量
		    birthday：	家人的生日


<h3>1．17、	</h3><h3>搜索家人接口</h3>  
【参数】  
>  

	uid:				用户id
	page:				当前页，默认为1
	perpage:			每页数量，默认为10
	fsearch:			提交搜索的标志，固定值1
	kw:					搜索的关键词,可以是电话号码或者名称
	usernamelist:		post形式发送到服务器的手机号码(或者新浪/腾讯微博的用户名)  
【调用方式】  
网站域名/dapi/ space.php?do=fmembers&uid=1&fsearch=1&kw=小宝  
【返回值】  
>  

	uid:			自己的用户id
	name:			自己的昵称
	avatar:			自己的头像
	fmembers：		自己的家人数量
	fmemberlist：家人列表【数组】
		uid			家人的用户id
	    name		家人的昵称
	    avatar：	家人的头像
	    note:		家人关系备注 
	    feeds:		家人动态数量 
	    fmembers：	家人的家人数量
	birthday：		家人的生日
	isfamily:		是否已经成为家人，1已经是家人，0不是
	noregister:		为1时，表示没有注册



 
<h3>1．18、	</h3><h3>家人申请接口</h3>  
【参数】  
>  
	
	uid:			用户id  
【调用方式】  
网站域名/dapi/cp.php?ac=friend&op=request  
【返回值】  
>  
	
	uid:				自己的用户id
	name:				自己的昵称
	avatar:				自己的头像
	fmembers：			自己的家人数量
	requestlist:申请人列表【数组】
		uid:			用户id
		phone:			电话号码
		name:			用户昵称
		avatar:			用户头像
		dateline:		申请时间

 
<h3>1．19、	</h3><h3>有奖任务列表接口</h3>  
【参数】  
>  

	do:			task
	uid:			用户id  
【调用方式】  
网站域名/dapi/space.php?do=task&uid=4  
【返回值】  
>  
	
	uid:			自己的用户id
	name:			自己的昵称
	avatar:			自己的头像
	tasknum:		未完成的有奖任务数
	tasklist:【数组】有奖任务列表
		taskid：	任务id
		image：		任务图标
		name：		任务名称
		note:		任务简介
		credit：	奖励金币数量


<h3>1．20、	</h3><h3>随机有奖任务提醒</h3>  
【参数】  
>  
	
	do:			task
	op:			rand
	uid:		用户id  
【调用方式】  
网站域名/dapi/space.php?do=task&op=rand&uid=4  
【返回值】  
>  
	
	taskid：	任务id
	image：		任务图标
	name：		任务名称
	note:		任务简介

 
<h3>1．21、	</h3><h3>有奖任务详情</h3>  
【参数】  
>  
	
	do:			task
	uid:		用户id
	taskid:		某个任务的id  
	
【调用方式】  
网站域名/dapi/space.php?do=task&&uid=4&taskid=1  
【返回值】  
>  
	
	taskid：	任务id
	image：		任务图标
	name：		任务名称
	note:		任务简介
	xyz:		是否已经满足条件、未满足条件下前往的页面（x.y.z）
 


<h2>第二部分 </h2><h2>上行接口部分</h2>
==================


<h3>2.1、	</h3><h3>普通登录接口</h3>  
【参数】  
>  

	username:		账号
	password:		密码
	iscookie:		是否保存密码，为1时保存   
【调用方式】  
网站域名/dapi/do.php?ac=login  
【返回值】  
>  
	
	data:
	 return: 返回的状态码，
		-1： 用户名或者密码为空
		-2： 用户名或者密码错误
		 1： 登录成功
	 
<h3>2.2、	</h3><h3>第三方登录接口</h3>  
【参数】  
>  
	
	username:		账号
	password:		密码
	logintype:		weibo: 新浪微博, qq：腾讯微博  
【调用方式】  
网站域名/dapi/do.php?ac=login  
【返回值】  
>  
	
	data:
		return:	返回的状态码
			-1：用户名或者密码为空
			-2：用户名或者密码错误
			 1：登录成功



 
<h3>2.3、	</h3><h3>注册接口</h3>  
【参数】  
>  
	
	username:			注册用户名(手机号)
	password:			密码
	invitecode:			邀请码  
【调用方式】  
网站域名/dapi/do.php?ac=register  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错



 
<h3>2.4、	</h3><h3>个人头像和昵称设置接口</h3>  
【参数】  
修改头像：  
>  
	
	Filedata:		文件上传变量
	avatarsubmit：	提交表单用的验证，设为1即可  
修改昵称：  
>  

	name:			昵称
	namesubmit：	提交表单用的验证，设为1即可

【调用方式】  
修改头像：网站域名/dapi/cp.php?ac=avatar  
修改昵称：网站域名/dapi/cp.php?ac=name  
【返回值】  
>  
	
	data:
		reward:
			credit:			返回的积分
			experience：	返回的经验


 
<h3>2.5、	</h3><h3>孩子信息设置接口</h3>  
【参数】  
>  
	
	babyname:			孩子姓名
	babysex:			孩子性别
	babybirthday:		孩子出生年月
	babyavatar:			孩子头像
	babysubmit：		提交表单用的验证，设为1即可  
【调用方式】  
网站域名/dapi/cp.php?ac=baby  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错



 
<h3>2.6、	</h3><h3>创建空间接口</h3>  
【参数】  
>  
	
	tagname:		空间名
	tagsubmit：		提交表单用的验证，设为1即可  
【调用方式】  
网站域名/dapi/cp.php?ac=tag  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错
 
<h3>2.7、	</h3><h3>申请成为家人接口</h3>  
【参数】  
>  
	
	uid:			自己的uid, 若登陆有保存，则用登陆保存的uid
	applyuid:		对方的uid
	gid:			申请的分组
	note:			申请时的附带信息
	addsubmit：		提交申请表单用的验证，设为1即可  
【调用方式】  
网站域名/dapi/ dapi cp.php?ac=friend&op=add  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错


<h3>2.8、	</h3><h3>同意成为家人接口</h3>  
【参数】  
>  
	
	applyuid:		申请人的uid
	gid:			分组id
	agreesubmit：	同意申请，设为1即可  
【调用方式】  
网站域名/dapi cp.php?ac=friend&op=add  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错

<h3>2.9、	</h3><h3>收藏动态</h3>  
【参数】  
>  
	
	id				被收藏的对象id
	idtype			被收藏的对象id类型(如：blogid, videoed)
	type			是增加还是取消收藏，1添加到收藏，0取消收藏  
【调用方式】  
网站域名/dapi/do.php?ac=feedlove  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错

<h3>2.10、	</h3><h3>评论接口</h3>  
【参数】  
>  
	
	id				被评论的对象id
	idtype			被评论的对象id类型(如：blogid, videoed)
	message			评论内容  
【调用方式】  
网站域名/dapi/do.php?ac= comment  
【返回值】  
>  
	
	msgkey：		信息提示码
	msg：			返回的提示信息
	error:			返回的错误的状态, 0无错误，1出错

 
<h3>2.11、	</h3><h3>参加活动接口</h3>  
【参数】  
>  
	
	id				活动id
	idtype			eventid
	message			我要参加活动!
	come			发布来源（iphone或者ipad，客户端生成）  
【调用方式】  
网站域名/dapi/do.php?ac=comment  
【返回值】  
>  
	
	data	【数组】
		selfreward		参加者的奖励【数组】
		credit			金币
		experience		经验
		toreward		活动发起人的奖励【数组】
		credit			金币
		experience		积分


<h3>2.12、	</h3><h3>表态接口</h3>  
【参数】  
>  
	
	id			被表态对象的id
	idtype		被表态对象的类型(eventid,blogid,vedioid,photoid)
	clickid		表态类型的id，一个id可以对应一个表态的类型，如：鲜花，雷人
	come		发布来源（iphone或者ipad，客户端生成）  
	
【调用方式】  
网站域名/dapi/cp.php?ac=click&op=add  
【返回值】  
>  
	
	data	【数组】
		reward			表态者的奖励【数组】
		credit			金币
		experience		经验

 
<h3>2.13、	</h3><h3>发消息（对话）接口</h3>  
【参数】  
>  
	
	touid		对方的uid
	pmid		对话列表的id
	message		消息内容
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（iphone或者ipad或者android，客户端生成）
	pmsubmit	提交信息的表单验证，设为1即可  
【调用方式】  
网站域名/dapi/ cp.php?ac=pm&op=send  
【返回值】  
>  
	
	msgkey：			信息提示码
	msg：				返回的提示信息
	error:				返回的错误的状态, 0无错误，1出错

<h3>2.14、	</h3><h3>修改头像接口</h3>  
【参数】  
修改头像：  
>  
	
	Filedata:			文件上传变量
	avatarsubmit：		提交表单用的验证，设为1即可  
【调用方式】  
修改头像：网站域名/dapi/cp.php?ac=avatar  
【返回值】  
>  
	
	data:
		reward:
			credit:		返回的积分
			experience：返回的经验

<h3>2.15、	</h3><h3>修改昵称接口</h3>  
【参数】  
>  
	
	name:				昵称
	namesubmit：		提交表单用的验证，设为1即可  
【调用方式】  
网站域名/dapi/cp.php?ac=name  
【返回值】  
>  
	
	data:
		reward:
			credit:		返回的积分
			experience：返回的经验
 
<h3>2.16、	</h3><h3>修改生日接口</h3>  
【参数】  
>  
	
	birth:				生日,格式(1989-08-12)
	birthsubmit：		提交表单用的验证，设为1即可  
【调用方式】  
网站域名/dapi/cp.php?ac=birth  
【返回值】  
>  
	
	msgkey：			信息提示码
	msg：				返回的提示信息
	error:				返回的错误的状态, 0无错误，1出错

 
<h3>2.17、	</h3><h3>参加有奖任务接口</h3>  
【参数】  
>  
	
	taskid	任务的id  
【调用方式】  
网站域名/dapi/cp.php?ac=task&op=do  
【返回值】  
>  
	
	data:  
		credit:			返回奖励的积分
		spacecredit：	返回领奖后总的积分


<h3>2.18、	</h3><h3>修改备注关系接口</h3>  
【参数】  
>  
	
	fuid					被备注人的uid
	note					关系备注名称
	changenotesubmit		1  
【调用方式】  
网站域名/dapi/cp.php?ac=friend&op=changenote  
【返回值】  
>  
	
	msgkey：				信息提示码
	msg：					返回的提示信息
	error:					返回的错误的状态, 0无错误，1出错

<h3>2.19、	</h3><h3>修改生日提醒接口</h3>  
【参数】  
>  
	
	fuid					被设置生日的人的uid
	notebirth				生日日期
	changenotesubmit		1  
【调用方式】  
网站域名/dapi/cp.php?ac=friend&op=changenote  
【返回值】  
>  
	
	msgkey：			信息提示码
	msg：				返回的提示信息
	error:				返回的错误的状态, 0无错误，1出错

<h3>2.21、	</h3><h3>单张图片上传接口</h3>  
【参数】  
>  
	
	Filedata		文件域【FILE】
	op				uploadphoto【照片上传】, uploadpic【日志的图片上传】
	topicid			相册id
	pic_title		照片描述  
	
【调用方式】  
网站域名/dapi/cp.php?ac=upload  
【返回值】  
>  
	
	data:
		picid:				图片id
		pic:				图片的url路径
		reward:
				credit:		返回的积分
		     experience：	返回的经验


<h3>2.22、	</h3><h3>发表照片接口</h3>  
【参数】  
>  
	
	title		图片数组array(picid1=>描述, picid2=>描述), 调用2.21单张图片上传接口op= uploadphoto。
	message		照片总体描述
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	photosubmit	1 如果设置了此变量，代表提交了数据  
【调用方式】  
网站域名/dapi/cp.php?ac=photo  
【返回值】  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验

注：发布界面中还需要调用：  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

<h3>2.23、	</h3><h3>转发照片接口</h3>  
【参数】  
>  
	
	photoid		照片id
	message		照片总体描述
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	photosubmit	1 如果设置了此变量，代表提交了数据,  无此变量代表是发布界面  
【调用方式】  
网站域名/dapi/cp.php?ac=rephoto  
【返回值】  
无photosubmit时，代表是发布的界面:  
>  
	
	data:
		photoid:		照片id
		message:		照片内容
		pic:			照片的图片
		countpic:		照片中包含的图片张数 
		
有photosubmit是，代表是提交了表单数据：  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验

注：发布界面中还需要调用：  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

<h3>2.24、	</h3><h3>发表日记接口</h3>  
【参数】  
>  
	
	subject		日志标题
	message		日志正文内容, 内容 + 图片<调用2.21单张图片上传接口op=uploadpic>  <组合为html>
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	blogsubmit	1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面  
	
【调用方式】  
网站域名/dapi/cp.php?ac=blog  
【返回值】  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验

注：发布界面中还需要调用：  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 


<h3>2.26、	</h3><h3>转发日记接口</h3>  
【参数】  
>  
	
	blogid		被转发的日志id
	subject		日志标题
	message		日志正文内容, 内容 + 图片<调用2.21单张图片上传接口op=uploadpic>  <组合为html>
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	blogsubmit	1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面  
【调用方式】  
网站域名/dapi/cp.php?ac=reblog&blogid=被转的日志id  
【返回值】  
没有设置blogsubmit时, 即发布时的生成界面：  
>  
	
	data:
		blogid:			被转发的日志id
		subject:		日志标题
		message:		日志内容<html>
		其他参数与发布时提交参数含义一样

注：发布界面中还需要调用：  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

设置了blogsubmit后，即提交了表单后：  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验

<h3>2.27、	</h3><h3>发表活动接口</h3>  
【参数】  
>  
	
	title			活动标题
	location		活动地点
	starttime		活动开始时间
	classid			活动类型id
	detail			活动正文内容, 内容 + 图片<调用2.21单张图片上传接口op=uploadpic>  <组合为html>
	friend			查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags			空间名
	friends			和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat				纬度（客户端生成）
	lng				经度（客户端生成）
	address			发布地址（客户端生成）
	come			发布来源（客户端生成, iphone或者ipad或者android）
	makefeed		1, 是否产生feed
	makeweibo		是否发布到微博，1代表是
	eventsubmit		1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面  
【调用方式】  
网站域名/dapi/cp.php?ac=event  
【返回值】  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验

注：发布界面中还需要调用：  
2.29  [活动分类接口](#活动分类接口)  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

<h3>2.28、	</h3><h3>转发活动接口</h3>  
【参数】  
>  
	
	title		活动标题
	location	活动地点
	starttime	活动开始时间
	classid		活动类型id
	detail		活动正文内容, 内容 + 图片<调用2.21单张图片上传接口op=uploadpic> <组合为html>
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	eventsubmit	1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面   
【调用方式】  
网站域名/dapi/cp.php?ac=reevent&eventid=被转发的活动id  
【返回值】  
没有设置eventsubmit时, 即发布时的生成界面：  
>  
	
	data:
		eventid:		被转发的活动id
		其他参数与发布时提交参数含义一样  

注：发布界面中还需要调用：  
2.29  [活动分类接口](#活动分类接口)  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

设置了blogsubmit后，即提交了表单后：  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验

<h3>2.29、	</h3><h3>活动分类接口</h3>  
【参数】[GET方式]  
无  
【调用方式】  
网站域名/dapi/cp.php?ac=event&op=eventclass  
【返回值】  
>  
	
	data:
		eventclass 【活动分类数组】
			classid:	 	分类id
			classname：		分类名称
			template:		分类的内容描述模板


 
<h3>2.30、	</h3><h3>发表视频接口</h3>  
【参数】  
>  
	
	subject		视频标题
	videourl	视频地址
	message		视频正文内容, 内容 + 图片<调用2.21单张图片上传接口op=uploadpic>  <组合为html>
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	videosubmit	1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面  
【调用方式】  
网站域名/dapi/cp.php?ac=video  
【返回值】  
>  
	
	data:
		credit:			返回的积分
		experience：	返回的经验  

注：发布界面中还需要调用：  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

<h3>2.31、	</h3><h3>转发视频接口</h3>  
【参数】  
>   
	

	subject		视频标题
	videourl	视频地址
	message		视频正文内容, 内容 + 图片<调用2.21[单张图片上传接口](#21单张图片上传接口)op=uploadpic>  <组合为html>
	friend		查看范围：1家人可见，2仅自己可见，0全站用户可见
	tags		空间名
	friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
	lat			纬度（客户端生成）
	lng			经度（客户端生成）
	address		发布地址（客户端生成）
	come		发布来源（客户端生成, iphone或者ipad或者android）
	makefeed	1, 是否产生feed
	makeweibo	是否发布到微博，1代表是
	videosubmit	1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面 
 
【调用方式】  
网站域名/dapi/cp.php?ac=video  
【返回值】  
没有设置videosubmit时, 即发布时的生成界面：  
>  
	

	data:
		videoid:		被转发的视频id  
		其他参数与发布时提交参数含义一样  

注：发布界面中还需要调用：  
2.33  [空间名称列表接口](#空间名称列表接口)  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 

设置了videosubmit后，即提交了表单后：  

	data:
		credit:			返回的积分
		experience：	返回的经验

<h3>2.32、	</h3><h3>发表我想说接口</h3>  
【参数】  
> 

		message		日志正文内容
		friends		和谁在一起uid 【数组】array(uid=>username,uid2=>username2)
		lat			纬度（客户端生成）
		lng			经度（客户端生成）
		address		发布地址（客户端生成）
		come		发布来源（客户端生成, iphone或者ipad或者android）
		makeweibo	是否发布到微博，1代表是
		isaysubmit	1 如果设置了此变量，代表提交了数据，没有设置，那么就是发布界面  
【调用方式】  
网站域名/dapi/cp.php?ac=isay  
【返回值】  
如果没有设置isaysubmit, 即发布界面上，得到的是默认的我说的句子列表：  
>  
		
		data:
			lid:		路上 句子列表 [数组]
			wid:		我说 句子列表 [数组]
		tid:			天气 句子列表 [数组]
		zid:			祝福 句子列表 [数组]

注：发布界面中还需要调用：  
2.34  [和谁在一起的人列表接口](#和谁在一起的人列表接口) 
  
点击发布后，即设置了isaysubmit，则返回值为：  
> 
	
	data:
		credit:			返回的积分
		experience：	返回的经验

<h3>2.33、	</h3><h3>空间名称列表接口</h3>  
【参数】【GET方式】  
无  
【调用方式】  
网站域名/dapi/do.php?ac=ajax&op=taglist    
【返回值】  
>  
	
	data
		taglist:【数组】  
			tagname	 	名称  



<h3>2.34、</h3><h3>和谁在一起的人列表接口</h3>  
【参数】【GET方式】  
无  
【调用方式】  
网站域名/dapi/do.php?ac=ajax&op=taglist  
【返回值】  
>   

		data
			friendlist:	【数组】
				fuid		 	用户uid
				fusername		用户名


