+++
title = "nginx don't gzip"
date = 2010-05-03T03:07:00Z
updated = 2010-05-03T03:20:04Z
tags = ["Debian", "GNU/Linux", "Nginx"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

找了很久，也看了一些文件<br /><br /><a href="http://serverfault.com/questions/84400/nginx-ubuntu-9-10-gzip-not-functioning">http://serverfault.com/questions/84400/nginx-ubuntu-9-10-gzip-not-functioning</a><br /><br /><a href="http://wiki.nginx.org/NginxHttpGzipModule">http://wiki.nginx.org/NginxHttpGzipModule</a><br /><br /><br />最後答案很簡單，也許不是真正的答案，只是一個 fix <br /><br />會造成一直沒有 gzip 的原因，很有可能是，我用來接 backend fastcgi 的時候 Accept-Encoding 的資訊掉了，nginx 跟前端是用 http version 1.1 跟  backend 是用 http version 1.0<br /><br />不管如何，也許是bug 或是設定的錯誤，目前把 nginx.conf 裡 gzip 的設定加上<br /><br />gzip_http_version   1.0;<br /><br />就可以了，先撐著吧
