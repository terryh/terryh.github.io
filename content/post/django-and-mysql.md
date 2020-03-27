+++
title = "Django and MySQL"
date = 2007-03-29T23:46:00Z
updated = 2007-11-06T09:25:37Z
tags = ["Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

最近在做的東西，是用 MySQL （懶，已經有 MySQL了，不想再裝 PostgreSQL 了），在資料庫上預設用 UTF8 編碼，在 Django 上，如果 DATABASE_ENGINE = 'mysql'，第一個 connection 都會下， SET NAMES utf8; 然後，之後的 Query 都會自己加 SET NAMES latin1; 大多時候，是正常，不過，有時是亂碼，奇怪就在，我把這一個有問題的結果，print 出來除錯時，螢幕是亂碼，可是在網頁上又可以變正常，真想掉眼淚<br /><br />這種情形，一開始用 Sqlite 開發的時候，也沒有，所以開發環境，還是跟實際一模一樣比較好<br /><br />真是很怪的情形，令我頭痛好幾個晚上，有點像是靈異現象了<br /><br />不過還好試一下舊的mysql engine ，還可以用，而且不會有這種怪情形，他只有會在connection 時下， SET NAMES utf8; 之後的 Query 不會加 SET NAMES latin1<br /><br />暫時用這一個好了，設定 settings.py 裡改成 DATABASE_ENGINE = 'mysql_old'<br /><br />作業環境，Debian_etch，python2.4.4，python-mysqldb-1.2.1-p2-4，mysql-server-5.0.32，Django svn 4866<br /><br />.. -*- mode: rst -*-
