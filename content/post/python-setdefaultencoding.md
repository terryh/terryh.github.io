+++
title = "Python setdefaultencoding"
date = 2008-03-26T02:24:00Z
updated = 2008-03-26T02:38:29Z
tags = ["Python"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

開發及程式執行環境，如果要執行環境的預設編碼<br /><br /><br />舉例，我要預設 utf8<br /><br />1)  加入 import sys; sys.setdefaultencoding('utf-8') /etc/pythonX.Y/sitecustomize.py<br /><br /><br />2)   加入 import sys; sys.setdefaultencoding('utf-8') /usr/lib/pythonX.Y/sitecustomize.py<br /><br />3) 程式開頭加入， reload(sys);sys.setdefaultencoding('utf-8')<br /><br />至於原因，及詳細細節請參考(不好意思，我說故事的能力還沒加強好)<br /><br /><a href="http://blog.ianbicking.org/illusive-setdefaultencoding.html">http://blog.ianbicking.org/illusive-setdefaultencoding.html</a>
