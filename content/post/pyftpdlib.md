+++
title = "pyftpdlib"
date = 2008-01-09T05:30:00Z
updated = 2008-01-09T05:56:13Z
tags = ["Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

沒有依附任何其他模組，或是函式，開發者一直都有在維護，可以簡單達成跨平台，去年在一個偶然的機會下，需要整合高效能的 Django site 及 FTP server，非常容易就可以客製成和 Django 同樣的認證機制，就可以不管用 Web 介面，或是 FTP 的介面，都是同一個個人的檔案系統，Web 整合更多的功能， FTP 介面則可以完成基本的認證，檔案的讀寫<br /><br />OO 的特性，可以用重載的機制，簡單的改成自己要的 FTP，我的玩法則是，完全控制，寫入檔案的檔名，有興趣的可以把玩一下<br /><a href="http://code.google.com/p/pyftpdlib/"><br />http://code.google.com/p/pyftpdlib/</a>
