+++
title = "uWSGI --vhost"
date = 2011-12-28T22:33:00Z
updated = 2011-12-28T23:02:12Z
tags = ["Python", "uWSGI", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://projects.unbit.it/uwsgi/"><img src="http://projects.unbit.it/images/logo_uWSGI.png" /></a>  <br /><br />用 uWSGI 來啟動 wsgi 的服務，除了傳統的方式，還可以一次管理多個 wsgi 的服務<br /><br />還有另外一種作法 Emperor 可以對特定資料夾裡所有的設定檔，個別管理，更適合作 PASS 服務的人，  <a herf="http://projects.unbit.it/uwsgi/wiki/Emperor">http://projects.unbit.it/uwsgi/wiki/Emperor</a><br /><br />我的需求沒有這麼大，只是一起跑多個 wsgi ，省一些記憶體，就可以了<br /><br /><br />用 daemontools 來啟動，這裡面的 buffer-size 有要吃外部的 post back 要加大，不然，預設的實在是太小，最重要的是預設值 PayPal<br />IPN callback 吃不下，收到錢還不知道，夠重要了吧<br /><br /><pre>#!/bin/bash<br /># default buffer-size is 4k 4096<br />exec setuidgid yourname uwsgi --buffer-size 32768 -s 127.0.0.1:3031 -p 3 -M --vhost<br /></pre><br />以在 Debian 上面的 nginx 裡面的設定範例<br /><br /><pre><br /> server {<br />listen   80;<br />server_name  yourcoolsite.com;<br />location /static {<br />    alias /yourstatic/folder/;    <br />}<br />location / {<br />    include     uwsgi_params;<br />    #uwsgi_pass   unix:/tmp/digez.sock;<br />    uwsgi_param UWSGI_PYTHONPATH /home/yourname;<br />    uwsgi_param UWSGI_CHDIR /home/yourname/yourcoolsite;<br />    uwsgi_param UWSGI_ENV DJANGO_SETTINGS_MODULE=yourcoolsite.settings;<br />    uwsgi_param UWSGI_MODULE application;<br />    uwsgi_pass   127.0.0.1:3031;<br /> }<br /><br /></pre><br />放在 /home/yourname/yourcoolsite/ 的 wsgi application.py script 範例<br />sys.path.append 那兩行，在 Django 1.4 以下，也就是 1.3.1 (含) 以下，都要加，比較不會有路徑的問題<br /><br />Django 目前的 Dev(或是 trunk 或是 github 上面 master) 開發版，已經改變 project 的路徑，所以不用再加了<br /><br /><pre># coding: utf-8<br />import sys<br />import os<br />sys.path.append(os.path.abspath(os.path.dirname(__file__)))<br />sys.path.append('..')<br />os.environ['DJANGO_SETTINGS_MODULE'] = 'settings'<br />                                                                                                                                     <br />import django.core.handlers.wsgi<br /><br />application = django.core.handlers.wsgi.WSGIHandler()<br /><br /></pre>
