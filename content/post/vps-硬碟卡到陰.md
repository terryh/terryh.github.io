+++
title = "VPS 硬碟卡到陰"
date = 2010-09-18T21:09:00Z
updated = 2010-09-18T21:12:11Z
tags = ["VPS"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

這幾天， ThrustVPS 上的 node 硬碟好像卡到陰的一樣，轉不太動<br /><br /><code><br />[root@www ~]#hdparm -tT /dev/xvda1<br /><br />/dev/xvda1:<br /> Timing cached reads:     2 MB in  2.11 seconds = 971.82 kB/sec<br /> Timing buffered disk reads:   16 MB in  3.14 seconds =   5.09 MB/sec<br />[root@www ~]#hdparm -tT /dev/xvda1<br /><br />/dev/xvda1:<br /> Timing cached reads:   7564 MB in  1.99 seconds = 3798.40 MB/sec<br /> Timing buffered disk reads:    6 MB in  3.59 seconds =   1.67 MB/sec<br />[root@www ~]#hdparm -tT /dev/xvda1<br /><br />/dev/xvda1:<br /> Timing cached reads:   6316 MB in  1.99 seconds = 3170.20 MB/sec<br /> Timing buffered disk reads:   84 MB in  3.03 seconds =  27.71 MB/sec<br />[root@www ~]#hdparm -tT /dev/xvda1<br /><br />/dev/xvda1:<br /> Timing cached reads:   6526 MB in  1.99 seconds = 3274.96 MB/sec<br /> Timing buffered disk reads:    4 MB in  3.13 seconds =   1.28 MB/sec<br />[root@www ~]#hdparm -tT /dev/xvda1<br /><br />/dev/xvda1:<br /> Timing cached reads:   5828 MB in  1.99 seconds = 2924.11 MB/sec<br /> Timing buffered disk reads:    8 MB in  4.03 seconds =   1.99 MB/sec<br />[root@www ~]#hdparm -tT /dev/xvda1<br /><br />/dev/xvda1:<br /> Timing cached reads:   3286 MB in  2.00 seconds = 1645.96 MB/sec<br /> Timing buffered disk reads:   10 MB in  4.47 seconds =   2.24 MB/sec<br />[root@www ~]#<br /></code>
