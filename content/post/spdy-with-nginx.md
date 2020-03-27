+++
title = "spdy with nginx"
date = 2013-07-28T20:27:00Z
updated = 2013-07-28T20:34:56Z
tags = ["Debian", "Nginx"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

這是一個加強版的協定，一開始由 Google 提出 <a href="https://zh.wikipedia.org/wiki/SPDY">https://zh.wikipedia.org/wiki/SPDY</a><br /><br />用 Apache 的朋友可以參考 <a href="https://code.google.com/p/mod-spdy/">https://code.google.com/p/mod-spdy/</a><br /><br />以下筆記，是以 Debian 用 nginx 官方的 deb 套件由為底的紀錄<br /><br />nginx 官方的套件 <a href="http://wiki.nginx.org/Install">http://wiki.nginx.org/Install</a><br /><br />Debian 用 wheezy,  source.list 可以加<br /><br /><code><br />deb http://nginx.org/packages/debian/ wheezy nginx<br />deb-src http://nginx.org/packages/debian/ wheezy nginx<br /></code><br /><br /><br />再來就是您的 nginx site 的設定了，下面是要加的部份，<br />也只有 listen 443 ssl spdy 那一行<br /><br /><code><br />server {<br />listen 443 ssl spdy;<br />#listen 443;<br /><br />server_name yourcoolhostname;<br />... <br />...<br />...<br />}<br /></code><br /><br />最後可以開 chrome 瀏覽器檢查連到網站的有沒有 SPDY 的連結<br />在瀏覽器的網址列打 chrome://net-internals/#spdy 就可以看到了<br /><br />或是可以用 <a href="http://spdycheck.org/">http://spdycheck.org/</a> 來檢查<br /><br /><br />目前 nginx 的 spdy 模組，只支援 spdy/2
