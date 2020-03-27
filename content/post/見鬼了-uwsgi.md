+++
title = "見鬼了 uWSGI"
date = 2011-12-05T22:17:00Z
updated = 2011-12-06T05:33:56Z
tags = ["uWSGI", "Gunicorn"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://projects.unbit.it/uwsgi/"><img src="http://projects.unbit.it/images/logo_uWSGI.png" /></a> <br />非常誇張，裝 uWSGI 遇到鬼打牆的情形，native Debian 可以， XEN VM 下面也可以，就其中一個  OpenVZ 的 Debian 裝不起來，老是跟我說 sys.path 有問題   Desktop Debian testing 和 XEN 裡面的 VM，都沒有問題   啟動的指令用 daemontools 來控制 <br /><pre>#!/bin/bash<br />cd /home/terry/webapp<br /><br />exec setuidgid terry uwsgi -s 127.0.0.1:3031 -p 2 --pp .. --env DJANGO_SETTINGS_MODULE=webapp.settings -w "django.core.handlers.wsgi:WSGIHandler()"<br /></pre>PS: 只好先用獨角馬 gunicorn <a href="http://gunicorn.org/"><img src="http://gunicorn.org/images/logo.png" /></a>
