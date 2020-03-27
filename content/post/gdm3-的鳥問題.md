+++
title = "GDM3 的鳥問題"
date = 2011-05-16T08:10:00Z
updated = 2011-05-16T08:22:24Z
tags = ["Debian"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

開發的桌機，一直都是跟 debian testing <br /><br />最近，更新完，發現爛了，原本的 auto login 沒辦法用了( 我一直都是這樣設得，沒辦法，這一台是自動下單用的 )<br /><br /><br />找了半天，才看到解法，只是還蠻鳥的<br /><br />編輯 /etc/gdm3/greeter.gconf-defaults 加一下，上面有一行， comment 掉的，可以 copy<br /><br />/apps/gdm/simple-greeter/disable_user_list true<br /><br /><br /><a href="http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=613491">炒翻了</a><br /><br />看完後，沒錯我是名副其實的 end user ，感覺還蠻幹的，浪費一堆時間
