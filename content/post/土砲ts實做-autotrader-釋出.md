+++
title = "土砲TS實做 AutoTrader 釋出"
date = 2010-01-06T05:53:00Z
updated = 2010-01-06T06:12:07Z
tags = ["Python", "程式交易", "AutoTrader"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

之前在 Plurk 上看到網友，自己寫程式下單的整套系統，在加上，Open Source 其實也有很多現成的套件，所以我用爬抓語實做一個像是 Trade Station 上用 Easy Language 類似的實做<br /><br />目前還不能下訊號，不過可以回測，寫策略，語法像 Easy Language, <br /><br />這是目前專案的連結，<a href="http://github.com/terryh/autotrader">http://github.com/terryh/autotrader</a><br /><br /><br />晚一點，會在補一下文件，還有策略程式範例，以後，就不管日盛改不改版，誰的報價源穩定，手續便宜，就用哪一家<br /><br />系統設計原則<br /><br />就是要非常簡單，非常白痴，國小的小朋友，也可以看得懂<br /><br />給你一個完整的程式語言功能，你要怎麼玩，就怎麼玩<br /><br />盡可能的語法像，Easy Language ，大家的腦袋才比較好轉彎<br /><br /><br />接下來的 TODO 就是把即時的報價，及監控寫完，就可以真的下訊號了，可以玩得還很多，可以一貫化，報價，策略監控，到下單，都可以一氣呵成<br /><br />PS:  最後要感謝日盛，要這麼常改版，沒有辦法維持一個穩定的版本，把客戶當北七，一直接拿客戶的錢來 Debug，才激發動力，讓我自己開發
