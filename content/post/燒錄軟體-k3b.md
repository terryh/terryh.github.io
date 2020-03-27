+++
title = "燒錄軟體 K3b"
date = 2004-11-26T06:32:00Z
updated = 2007-11-05T06:42:35Z
tags = ["GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<br /><h1><a href="http://www.k3b.org/">K3b</a></h1><br />K3b 是在 Linux 下開發的燒錄軟體，大多是人機介面的整合，原本是針對 KDE 作最佳化，但是其實不管是哪個 window manager 都可以用, Nero 有的功能，大多都有，有興趣的可以試試。如果是 <a href="http://www.debian.org/">Debian</a> 的話有現成的 deb 可用 。<br /><br />請在 <strong>/etc/apt/source.list</strong> 加入官方網站的 deb 位址<br /><br />用 woody (stable ) 的加入<br /><br /><strong>deb http://www.planet-moll.de/debian woody main</strong><br /><br />用 sarge 也就是現在的 testing  加入下一行<br /><br /><strong>deb http://www.planet-moll.de/debian sarge main</strong><br /><br />在執行<br /><br /><strong>apt-get update</strong><br /><br /><strong>apt-get install k3b</strong><br /><br />安裝完了，就輸入 k3b 試試看合不合用了
