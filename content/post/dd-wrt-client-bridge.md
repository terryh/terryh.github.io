+++
title = "DD WRT Client Bridge"
date = 2015-05-02T20:21:00Z
updated = 2015-05-02T20:29:13Z
tags = ["GNU/Linux", "生活雜記"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

想要連接，兩間房子的網路，失敗及成功方法<br /><br />目的希望可以用無線的方式，分出網路到同一棟大樓，不同樓層，兩個陽台，目視可見，不用再重新申請網路<br /><br />失敗經驗<br /><br /><br />目前的硬體，主要的 Router AP ，原廠韌體，接 HINET 家用光纖，放九樓陽台 <br /><a href="http://www.asus.com/tw/Networking/RTN18U/">RT-N18U</a><br /><img src="http://www.asus.com/media/global/products/JHORgaVSKoY9H7cG/P_setting_fff_1_90_end_500.png" /><br /><br /><br /><br />另一台放在不同樓層的無線 AP，刷 DD WRT 韌體，放四樓陽台<br /><a href="http://www.tp-link.tw/products/details/?categoryid=238&model=TL-WR1043ND+V1">TP-LINK TL-WR1043ND V1</a><br /><img src="http://www.tp-link.tw/resources/images/products/gallery/TL-WR1043ND-01_1_1.jpg" /><br /><br /><br /><br />N18U<br />標準 AP 設定方式，另外固定無線頻道，我固定頻道 6，設定 WDS 可以連線的 AP mac address  <br />Address 192.168.1.1 netmask 255.255.255.0 <br />DHCP server on<br />DHCP 分配 IP 範圍 192.168.1.100 ~ 192.168.1.254 <br />WPA2/Personal AES<br /><br />WR1043ND<br /><br />把 WAN disable<br />IP  位置設定 192.168.1.2<br />DHCP server off<br />Wireless mode 選 Client Bridged<br />SSID 及密碼和  N18U 相同 <br /><br />重新開機後，電腦，接 WR1043ND 的網路線，是可以上網，但是大約幾分鐘後，網路就會斷，用 telnet 連到<br />WR1043ND 的機器，去連線，也是一段時間後就會斷，可以由用網路線接 WR1043ND 的上網的電腦，重新取得 ip 連線，又可以回復<br /><br />實際把上網電腦，設成固定 IP 及路由，也是無法連線，試著，在 WR1043ND 上面設定靜態路由，也沒辦法，<br /><br />可能是我的網路概念，還不夠清楚，所以就放棄了，尤其覺得一開始都是可以連線，大約幾分鐘後，斷線後，一定要重新 DHCP 得到 IP<br />才能恢復連線，感到不穩定<br /><br /><br />最後成功方法解法很簡單，反過來 <br /><br />Hinet 接 WR1043ND 當成主要的無線 Router，反過來，N18U 開成無線中繼模式，這時用 N18U LAN 接著上網電腦，就可以連線了<br />速度，比一半，在少一點，不過堪用了<br /><br />原來，原廠的韌體，簡單好用，少花一些時間，會在直接買一台，同牌的支援應該更沒問題<br /><br />接了，賣家送的 8db 天線，真的有差別，訊號的強度，好很多，帶來的就是連線速度的穩定性<br /><br />以上，簡單的經驗分享<br /><br />
