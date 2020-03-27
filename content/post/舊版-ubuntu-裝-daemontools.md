+++
title = "舊版 ubuntu 裝 daemontools"
date = 2010-09-07T20:02:00Z
updated = 2010-09-11T01:50:01Z
tags = ["GNU/Linux", "Daemontools"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://www.ubuntu.com/"><img src="http://lh6.ggpht.com/_Bsjm2Qp0Duc/TIrtex7QQVI/AAAAAAAAA-I/Q1jVUxMwhgI/s800/ubuntu_logo.svg.png" /></a><br /><br />舊版的 ubuntu 裝 daemontools 會有的問題，原本一直參考的網頁爛了，自己作一下筆記<br /><br /><code><br />sudo apt-get install daemontools daemontools-run<br /></code><br /><br />建立這一個檔案，讓他可以開機執行<br />/etc/event.d/svscanboot ，檔案內容<br /><br /><code><br />start on runlevel 2<br />start on runlevel 3<br />start on runlevel 4<br />start on runlevel 5<br /><br />stop on runlevel 0<br />stop on runlevel 1<br />stop on runlevel 6<br /><br />respawn<br />exec /usr/bin/svscanboot<br /></code><br /><br />執行一下<br /><code><br />sudo initctl start svscanboot<br /></code><br /><br />其他在 /etc/service/  下的設定，照舊即可<br /><br />這是一個，簡單的 hudson 的 run file<br /><code><br />#!/usr/bin/env bash<br />cd /home/hudson<br />su -s /bin/sh hudson -c "exec envuidgid hudson java -jar /home/hudson/hudson.war"<br /></code><br /><br /><br />ps: 當然，很多時候，會用 Debian，用舊版的 ubuntu 當然也是因為在團隊工作的環境，不是你要用那一版就用那一版，沒有原因，沒有為什麼，大頭會決定
