+++
title = "測試一下 Django threading mode"
date = 2008-06-04T16:25:00Z
updated = 2008-06-04T16:33:17Z
tags = ["Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

之前有些一篇， <a href="/2008/05/prefork-or-threaded.html">prefork or threaded</a> 之中提到的 Internal Server Error 大約找到原因了，還不是非常的確定就是了，原因是資料庫，覆載太重了，我太常跑一些有的沒的，我的電腦真是太可憐了，所以接下來，網站，應該會衝 threade 的模式試試看
