+++
title = "Deabin 2.6.24"
date = 2008-04-07T18:56:00Z
updated = 2008-04-09T21:48:34Z
tags = ["Debian", "GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

有用 Debian  的朋友，如果您的無線網卡用的是 ipw3945，跟著 testing 的人，現在官方是建議用 iwlwifi 了，記得安裝 firmware-iwlwifi，還有 kernel module 要有 iwl3945，安裝後，原本的無線裝置，會變成 wlan0，相對配合的設定，要一起修改<br /><br />我的筆電原來的對應網路裝置是 eth1，都要修改成 wlan0<br /><br /><br />/etc/network/interfaces 檔案裡，eth1 變成 wlan0<br />還有砍掉<br />/etc/udev/rules.d/z25_persistent-net.rules 檔案裡，有關 eth1 的部份，他重開機後，第一次會重抓<br /><br />接著就恭喜你，可以重新無線遨遊了<br /><br />參考資料 <a href="http://wiki.debian.org/iwlwifi">http://wiki.debian.org/iwlwifi</a>
