+++
title = "Python string isalpha"
date = 2014-04-13T20:45:00Z
updated = 2014-04-16T17:37:52Z
tags = ["Python"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://4.bp.blogspot.com/-UGFRW6kRwfg/TIr8qtVyOKI/AAAAAAAAA-4/K3_9r29LWW0/s1600/500px-Python_logo.svg.png" imageanchor="1" ><img border="0" src="http://4.bp.blogspot.com/-UGFRW6kRwfg/TIr8qtVyOKI/AAAAAAAAA-4/K3_9r29LWW0/s320/500px-Python_logo.svg.png" /></a><br />筆記一下<br /><br />今天追蹤一個問題<br /><br />程式裡用了類似 u"中文".isalpah() 的比較方式<br /><br />實際上的中文，是由資料庫傳回的值<br /><br />是我太肉腳，還是這一個 function 命名的原意不明<br /><br />這樣會傳回 True<br /><br />參考文件 <a href="https://docs.python.org/3.4/library/stdtypes.html#string-methods">https://docs.python.org/3.4/library/stdtypes.html#string-methods</a><br /><br /><br />我目前 workaround <br /><br />u"中文".encode("utf8").isalpha()<br /><br /><br /><br />PS: 所有該死的事，都是起源於 Workaround <br /><br />
