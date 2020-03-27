+++
title = "哇哈哈 Good bye Internal Server Error"
date = 2008-09-29T04:56:00Z
updated = 2008-09-29T05:39:09Z
tags = ["Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

首先，這是一篇自首的白爛文，由於學藝不精，基礎不好，所以我的 Django Site 一直被<br /><br />Internal Server Error 咬到，已經兩個星期沒有發生了，應該算解對了<br /><br />事由<br /><br />我的 Django Site 是用 Fastcgi 的方式，跑在 Lighttpd 後面，不過，我是用 <a href="/2008/05/supervisor-django.html">supervisor</a> 來控制 Django ，所以應該都不會死掉才對<br /><br />問題<br /><br />不管，跑 thread 或是 prefork ，跑久了，都會有 Internal Server Error 出現，也就是我的 Django Site 的 process 死了，一直找不到原因，不過發生這種情形的時候，大多 Django 的 process 已經 fork 到一大串啦，分析網站流量，應該還不至於出現這種情形才對，除了幾個背後跑的分析工作比較吃資源，所以一直以來，我都是蠻烏龜的先擺著(雖然男子漢，是絕不可以這樣的)，不過，一星期，大概都有一次 Internal Server Error 發生，必須重跑 Django Site 才可以活過來<br /><br /><br />分析結果，大多是 Backgroud 的程式，使用資料庫太兇了，supervisor 以為我的 Django Site 掛了，所以就又幫我重開，可是舊的 Kill 不掉，就這樣，我的系統越跑越慢，慢到，資料庫不回應，就算掛了，Lighttpd 把 user request 送到，Django 的 Fastcgi 時，就變成 Internal Server Error <br /><br />初步解法<br /><br />真的很簡單<br /><br />只要在 Lighttpd 的 fastcgi server 裡的設定，加<br /> "max-procs" => 5,<br /><br />這樣就會控制住總量啦，這樣，Lighttpd 和 supervisor 可以合作好一點<br /><br />我是只要 5 隻就夠了，就在也沒有 Internal Server Error 了<br /><br />期待，我的 Django Site 下一次真的被網友打到爆
