+++
title = "web backend service in golang "
date = 2016-09-28T01:38:00Z
updated = 2016-09-28T01:38:22Z
tags = ["Golang", "Web"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

先前後端開發 web service 大多是以小型的 web framework echo 來做基礎開發<br /><br /><a href=" https://github.com/labstack/echo">https://github.com/labstack/echo</a><br /><br />到了後來，因為他新版 v2 api 的介面修改，包了另一個 http engine fasthttp 的模組，雖然多了一層的彈性<br /><br />多了一個選擇，但是在 golang 1.7 版以後，標準的函式庫已經包含了 context ，所有 framework 要解決的問題<br /><br />幾乎都可以用標準函式庫，就全可以解決了，也可以真正體會 composition 組件式的架構方式，第三方的函式也更容易整併<br /><br />請務必試試看，用 golang 標準的函式庫，加上一些第三方的函式，組建 web service<br /><br />更新待續
