+++
title = "CMFMailadd 0.2 Alpha Release"
date = 2005-04-29T01:33:00Z
updated = 2007-11-05T06:44:01Z
tags = ["Python", "Zope"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<br /><h1>短命的 CMFMailadd 0.1 Alpha</h1><br />說起來真是丟臉，試一下發現，<a href="cmfmailadd">01</a> 版的預設型態是 News Item 時會有問題，趕快解決。<br /><br />其實預設型態必須有 <code>edit</code> 這一個 method，而且我是用下面的方式修改內容:<br /><pre><br />     entry.edit(text_format='structured-text,text=entry_body)</pre><br />下載 <a href="http://www.zope.org/Members/terryh/Packages">CMFMailadd 0.2</a><br /><h1>詳細說明</h1><br />詳細說明請見 <a href="cmfmailadd">CMFMailadd 01 Alpha Release</a>
