+++
title = "Install Dropbox on Debian"
date = 2011-04-14T20:23:00Z
updated = 2011-04-17T07:13:03Z
tags = ["Debian", "GNU/Linux", "Dropbox"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="http://dropbox.com/static/images/logo.png" /><br /><br />小筆記安裝 ubuntu 的 Dropbox 安裝包，到 Debian testing 上面<br /><br />照往例，一定不是很乾淨的作法，我才寫筆記<br /><br /><br /><br />到 Dropbox 下載 Linux 64(OR 32) 下面的安裝包<br /><br /><a href="http://www.dropbox.com/downloading?src=index">http://www.dropbox.com/downloading?src=index</a><br /><br />下面就是指令筆記，因為 Ubuntu 和 Debain 這一個相依關係名稱不同<br /><br />假設我們下載的名稱是 nautilus-dropbox_0.6.7_amd64.deb<br /><br /><br />以此為範例，安裝要有 root 權限<br /><br />dpkg-deb -x nautilus-dropbox_0.6.7_amd64.deb tempdir # 解開到 tempdir<br /><br />dpkg-deb --control nautilus-dropbox_0.6.7_amd64.deb tempdir/DEBIAN # control 放到 tempdir/DEBIAN 下面<br /><br />vim tempdir/DEBIAN/control # 編輯 control 檔，將安裝的時候抱怨的  libnautilus-extension1 (>= 1:2.22.2) 改成 libnautilus-extension1 (>= 2.22.2) <br /><br />dpkg-deb -b tempdir nautilus-dropbox_0.6.7-terry_amd64.deb # 重新包一包，取一個名字<br /><br />dpkg -i nautilus-dropbox_0.6.7-terry_amd64.deb # 安裝自己包的那一包，就可以了<br /><br /><br /><br />接下來，看看，自己的應用程式選單裡，應該就有 Dropbox 了
