+++
title = "JAVA 在 Debian 下中文方格"
date = 2009-12-06T00:08:00Z
updated = 2009-12-06T17:10:55Z
tags = ["Debian", "GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

自己紀錄一下，免得以後忘記，假設你跟的是 lenny<br /><br /><br />/etc/apt/sources.list 中有<br /><br />deb http://www.backports.org/debian lenny-backports main contrib non-free<br /><br />有裝<br /><br />sun-java6-jre sun-java6-jdk sun-java6-bin<br /><br />之中 java fonts 的部份，在 sun-java6-jre 的套件之中，由於，我想用的中文字型是放在，/usr/local/share/fonts/openfonts 之下的 odosung.ttc ，至於 ODOFonts 的下載點可以參考，之前整理的<a href="/2009/11/debian.html">最近裝 Debian 的資料</a><br /><br /><br />所以先到<br />cd /usr/lib/jvm/java-6-sun/jre/lib/fonts/  建一個 fallback 的資料夾，<br /><br />mkdir fallback<br /><br />cd fallback<br /><br />ln -s /usr/local/share/fonts/openfonts/odosung.ttc<br /><br />mkfontdir<br /><br />mkfontscale<br /><br />好了，收工<br /><br /><br /><br />參考 <a href="http://linuxtoy.org/archives/java_chinese.html">http://linuxtoy.org/archives/java_chinese.html</a>
