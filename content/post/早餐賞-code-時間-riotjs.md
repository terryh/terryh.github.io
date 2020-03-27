+++
title = "早餐賞 code 時間 riotjs"
date = 2013-12-04T17:38:00Z
updated = 2013-12-04T18:09:52Z
tags = ["JavaScript"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

javascript MVP 框架，小是特點，有 jquery 版，及非 jquery 版<br /><br />原始碼當然是挑短看，看他的手路怎麼樣<br /><br /><br /><a href="https://github.com/moot/riotjs/blob/master/jquery.riot.js">https://github.com/moot/riotjs/blob/master/jquery.riot.js</a><br /><br />基本的架構，就是架構在 javascript 的 event 上面<br /><br />就在用了 $.observable( 你的MODEL Object 包上jQuery的 event) // 就是 on one trigger off<br /><br /><br />很多東西，都可以自己刻，將自己定義的 model binding event name，然後，再主要的應用程式邏輯裡<br />去對應處理前端的反應，及呈現，看起來，就是直接切入原本熟悉用 jQuery 的前端工程師，不用一下子跳太遠，<br />有時間可以來實作一下，比較能感受<br /><br /><br /><br /><br />
