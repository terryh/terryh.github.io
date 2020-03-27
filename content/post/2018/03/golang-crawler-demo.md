+++
title = "golang crawler demo"
date = 2018-03-06T00:26:00Z
updated = 2018-03-06T02:35:52Z
tags = ["Golang"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

最近有個面試的回家作業，做了一個簡單的爬蟲<br /><br />單純只有爬一下，家樂福，還有大潤發的網站，一家是用 HTML 不斷的翻頁下去，爬完休息<br />另一家，直接找他的 json api ，直接抓 api 的結果就可以了<br /><br />目前整個 code base 挑出來的毛病，或是說，用一個微小的專案，來看軟體開發這件事，需要具備的東西<br />也是一個不錯的自我成長方式，可以一步一步看，目前用 golang 來實作一些，像是後端服務的一些處理模式<br /><br />會寫出來，主要是也許會對剛好有機會碰到，這些問題的人有幫助<br /><br />code reference <a href="https://github.com/terryh/honestman">https://github.com/terryh/honestman</a><br /><br />我先列一些一般來說用 golang 來寫一些像是 api 服務的問題，或是比較像是軟體的架構模式來討論<br /><br />1) crawler (爬蟲) 的 go routine 模式<br /><br />2) 要用 ORM 來抽象化 SQL 的操作好，還是不用 ORM 來操作<br /><br />3) 你需要用 framework 嗎？<br /><br />4) simple test case and benchmark ?<br /><br /><br />由於，這其實是一個可大可小的題目，但是，我還是來簡單說一下，目前，一般用 golang 做 web service ，或是給手遊用的<br />後端服務介面，或是手機應用程式的 api 介面，大概會用哪一些函式庫<br /><br />如果，開發團隊人員不多，對整個 http/s 或是網路服務認識不多，會選，既有的框架<br />目前，比較受歡迎的有<br /><br /><a href="https://github.com/gin-gonic/gin">https://github.com/gin-gonic/gin</a><br /><br /><a href="https://github.com/astaxie/beego">https://github.com/astaxie/beego</a><br /><br /><a href="https://github.com/labstack/echo">https://github.com/labstack/echo</a><br /><br />我個人比較推薦是相容於 golang http library http.HandlerFunc 的 framework<br /><br />如果不要框架，選擇更多，但是，這種人必須比較專業，也要更了解要處理的問題，還有 golang standard library ，因為，要有能力可以判斷，<br />像大家建議的 COMPOSITION 方式 <a href="https://www.youtube.com/watch?v=194blNHDdd0">https://www.youtube.com/watch?v=194blNHDdd0</a><br /><br />自己組建比較多，就是選用一個 http router dispacher <br />這個則是有很多的參考，或是選擇 <a href="https://github.com/julienschmidt/go-http-routing-benchmark">https://github.com/julienschmidt/go-http-routing-benchmark</a><br /><br />剩下的大概就是組建自己的服務了<br /><br />需要  HTML, JSON render 的，或是需要驗證身份，或是希望引用 ORM 來達到和 DB 層的抽象化，這些每一種都一個選擇，伴<br />隨著也都是取捨的問題<br /><br />未完待續，接下來，上面列出的點，會做作小筆記，也希望對需要的人有幫助 ;-)<br /><br />
