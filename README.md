# odproxy

然后回到上面，修改ASSET_URL这一行

最后“保存并部署”，从左上角退出

然后打开“触发器”，先在“自定义域”中，添加要作为反代服务的域名，等待3~5分钟后刷新页面，直到“证书”列显示为“有效”。

在下方点击“添加路由”，同样输入反代域名，但这里注意一点，最后一定要
加上/*
加上/*
加上/*
否则会提示指向被禁止的IP不能下载。
----

区域选择对应的根域名即可。

接下来删除掉自定义域

打开你的域名dns页，手动添加一条A记录解析，解析到你的自选IP。
并且点掉橙色云朵，改为“仅限DNS”。

保存你的解析，至此，完成✅！
注意事项：

自选IP需要自己找，文中的示例不一定一直可用。

一些FAQ：
服务搭建好了，怎么用？
下载时将前面的xxxxx-my.sharepoint.com替换为你的反代地址即可，也可以用于配置自建云盘服务。
这里有一个Demo，你可以尝试一下 https://www.sunbangyan.cn/s/ojuL 

自选IP咋搞？
参照这个项目 https://github.com/XIU2/CloudflareSpeedTest/

为什么worker没有效果甚至连接不上？
（针对某些地区）
可能是当地运营商屏蔽/干扰了Cloudflare cdn的IP，建议用idm开32线程直接从源站下载。
目前来看移动（香港直连）的效果相对最好。

