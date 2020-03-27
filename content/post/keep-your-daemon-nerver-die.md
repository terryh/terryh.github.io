+++
title = "Keep your daemon nerver die"
date = 2008-02-16T19:43:00Z
updated = 2008-02-22T16:42:06Z
tags = ["GNU/Linux", "Python", "MSN BOT"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

有看過，黃金羅盤的人，一定都希望，你的 daemon 可以永遠不死 (逃)<br /><br />這一篇是有關於系統工具的，如果，沒有興趣，不要在看下去了<br /><br />我開始認真說，在許久以前，在裝 Qmail 的時候，有個工具，他叫 <a href="http://cr.yp.to/daemontools.html">daemontools</a><br /><br />功用就是讓你的 long run daemon (長跑的執行程序，我翻這樣，請大大息怒)<br /><br />永遠不死，而 <a href="http://supervisord.org/">supervisor</a> 就是這樣的工具 Python 版，有什麼好處，還要說嗎？<br />當然是簡單易用，跨平台，還不用編譯，就可以上啦 ;-)<br /><br /><a href="http://supervisord.org/">Supervisor</a><br /><br />PS: 我已經偷用很久了，最近多養一隻 daemon 才想到，養在這 <a href="http://blog.lifetaiwan.net/search/label/MSN%20BOT">MSN BOT</a><br /><br />PS2:daemon會死的原因，有很多，也非常有可能自己程式寫的不好，到處都是 memory leak ，或是耗盡系統給你的資源，或是網路程式斷線啦，可是你沒有處理這一部份，造成異常，找出問題才是重要的，不要以為有不死鳥可以用，就開始擺爛<br /><br />PS3: 沒事啦，有感而發，想買 PS3 啦
