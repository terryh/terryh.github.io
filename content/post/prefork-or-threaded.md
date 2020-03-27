+++
title = "prefork or threaded"
date = 2008-05-07T18:32:00Z
updated = 2008-05-08T02:37:21Z
tags = ["Debian", "GNU/Linux", "Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

開發好的網站程式最終還是會裝在網站伺服器上，開放對外面的服務，實際考驗你寫程式的效能，及整個架構能否負荷對所有網民的請求<br /><br />這是最近試過的組合<br /><br />Lighttpd + fastcgi + Django prefork<br /><br />Lighttpd + fastcgi + Django threaded<br /><br />Lighttpd + scgi + Django prefork<br /><br />Lighttpd + scgi + Django threaded<br /><br />用 apache 附的 ab 作壓力測試 ，concurrency 100, 1000 request 100, 1000<br /><br />Django 都是使用 local unix sock 的方式跑，用預設的 maxchildren=50 請求頁面是一個 Django 的 cache 頁面，有 6個 MySQL 的查詢<br /><br />環境<br /><br />Debian Linux  2.6.24-1-686，Lighttpd 1.4.19，MySQL 5.0.51a， Python2.5.2，python-flup 1.0-1，python-mysqldb 1.2.2-6，Django version 0.97-pre-SVN-7480<br /><br />IBM X60 CPU Intel Core Duo 1.83 RAM 1G<br /><br />調整 Django 的架構方式得到的結論<br /><br />效能上 scgi 和 fastcgi 並無太大的差別<br /><br />所以只比較 prefork，threaded<br /><br />效能 <br />threaded > prefork<br />成功完成 web 請求數最多，最快<br />threaded  Requests per second:    438.89 [#/sec] (mean)<br />prefork  Requests per second:    129.53 [#/sec] (mean)<br />穩定度<br />prefork > threaded<br />threaded 模式運作一段時間後會出現 Internal Server Error，沒有回應<br /><br />兩種模式，在壓力過大的時候，都會出現無法回應，要等待才能回復，這是正常的現象，因為，Lighttpd pass 給 Django，也要 Django 來得及回應<br /><br />不過，在真實的運作中， threaded 出現的 Internal Server Error 是不會回復的，需重新啟動 Django 才行<br /><br />結論就是，先不要對 threaded 的效能流口水，prefork 擋著先<br /><br />希望有大大可以有建議<br /><br />參考資料<br /><br /><a href="http://www.alrond.com/en/2007/jan/25/performance-test-of-6-leading-frameworks/">http://www.alrond.com/en/2007/jan/25/performance-test-of-6-leading-frameworks/</a><br /><a href="http://timchen119.blogspot.com/2007/06/thread-dying-problem-may-fixed-in.html">http://timchen119.blogspot.com/2007/06/thread-dying-problem-may-fixed-in.html</a>
