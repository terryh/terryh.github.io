+++
title = "Django POP3Backend"
date = 2007-04-26T23:57:00Z
updated = 2007-11-06T09:25:47Z
tags = ["Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

最近作一個公司內部簡單的應用，希望不要讓使用者再去記憶更多密碼，所以 POP3Backend 於是誕生，可以直接用公司的  POP3 Server 來作認證，會先試試 POP SSL 來連，不行才用一般的 POP 連結，真的是很短啦，有一點陽春，用了一個需外裝的 python dns 模組，來查網域的 MX 資料，還有很大的改善空間，不過還是可用啦，一樣，版權沒有，自己取用，責任自負<br /><br />雖然也很想用 LDAP，不過，內部系統雜亂的歷史包袱，還一時改變不了，還是先撐一下吧，說到認證，不免要抱怨一下，什麼時候，台灣才有正式的非商業，OpenID service provider 壓<br /><br />連結在這 http://www.djangosnippets.org/snippets/203/<br /><br />參考資料<br /><br />http://www.carthage.edu/webdev/?p=12 ，LDAP Authentication in Django with Backends<br />http://www.djangoproject.com/documentation/authentication/ ，User authentication in Django<br /><br />.. -*- mode: rst -*-
