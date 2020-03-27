+++
title = "supervisor 讓你的 Django 活久一點"
date = 2008-05-02T02:44:00Z
updated = 2008-05-04T18:45:23Z
tags = ["Debian", "GNU/Linux", "Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

過去曾經提過一篇<a href="/2008/02/keep-your-daemon-nerver-die.html">Keep your daemon nerver die</a>，有關 <a href="http://supervisord.org/">supervisor</a> 的文章，今天，要小記一下， 用supervisord 來控制 <a href="http://www.djangoproject.com/">Django</a> ，若是發現程式運作發生問題，會自動幫你重新啟動<br /><br />這是放在設定檔  /etc/supervisord.conf 裡的片段<br />digez 就是我自己取的名字，因為是要讓 supervisor 來監控，所以 daemonize 設成 false，要注意的是 sock file 的權限，必須是 user www-data 可以讀寫的權限，我的環境是 Debian testing, python 2.5.2<br /><br /><code><br />[program:digez]<br />command=/home/web/digez/manage.py runfcgi daemonize=false socket=/home/web/run/digez.sock pidfile=/home/web/run/digez.pid<br />user=www-data<br />autostart=true<br />autorestart=true<br />stdout_logfile=/var/log/digez.log<br /></code>
