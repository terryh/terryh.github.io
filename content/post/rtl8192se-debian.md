+++
title = "rtl8192se debian"
date = 2010-03-11T17:40:00Z
updated = 2010-05-03T03:20:30Z
tags = ["Debian", "rtl8192se"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在 lenovo 上面要裝 Debian 如果是用到 RealTek rtl8192se，現在沒有好一點的支援，不過，還是可以有可用的 linux driver 可撐一下<br /><br />心得教訓<br /><br />不是新的東西或是 driver 就是好的，lenovo 新的都是 cost down 的產品，不然就不會沒事 intel 或是 atheros 的 mini pci 無線卡不用，要換 RealTek 的，還有買東西之前要確定 Linux 的支援，還有穩定性<br /><br />心得分享<br /><br />原廠 RealTek 網站上面那一個最新的，我裝了用起來，反而是有問題的，連上一會後，會斷線，但又可以偵測到AP的訊號，還好有一版是給 64bit 用的驅動程式<br /><br /><a href="http://launchpadlibrarian.net/34090326/rtl8192se_linux_2.6.0010.1012.2009_64bit.tar.gz">http://launchpadlibrarian.net/34090326/rtl8192se_linux_2.6.0010.1012.2009_64bit.tar.gz</a><br /><br />目前還堪用，無線AP就在我座位後面，訊號大約，只有 60%， 先撐一下好了， 60% 的訊號，還是比小朋友出走去換一塊 intel 5100 好，被使用 windows xp 的主管笑很久了，電腦是要拿來用的，不是要拿來研究了，終於可以把我那一隻很 low 的 USB 外接式的無線網卡拔下來，不然一整個沒有用 notebook 的感覺，這星期下來，下班時間，一直在找答案，真的還蠻幹的，希望以後用 Debian 的開發效率可以狂電他們，最後，還是除了，client 的部份，都是放在 linux server 上
