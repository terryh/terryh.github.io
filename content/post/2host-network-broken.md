+++
title = "2HOST network broken"
date = 2010-07-26T17:23:00Z
updated = 2010-07-27T07:33:57Z
tags = ["GNU/Linux", "新聞", "VPS"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

連續兩天，2HOST 的網路都有問題，這是一直以來，讓我覺的他們的服務唯一不穩定的因素，所以，把 DigEZ 搬到 ThrustVPS 西岸 LA 的機房，一開始，我不是很喜歡 ThrustVPS，大概是他們有限制 vcpu core ，所以入門的 VPS 的 CPU 表現都不好，不過，如果 CPU 一直都不是吃很重，倒也不失是一個很好的選擇<br /><span style="font-size:180%;"><br />ThrustVPS優點</span><br /><br />西岸機房，網路穩定，延遲低，抓學速網路檔案，大約 10M，比(兩)光世代還快<br /><br />新機器，硬碟讀寫快，有 raid 10<br /><br />服務效率高， kernel 版本較新<br /><br />便宜，找不到西岸機房，更便宜的了(不然都找到德國去了)<br /><span style="font-size:180%;"><br />ThrustVPS缺點</span><br /><br />CPU 資源受限，效能較差，redis-benchmark 很明顯，效能不彰<br /><br />PS: 已經兩天了，我的 2HOST 還是連不到，好險頻寬大，有備份，搬家迅速<br />更新，2HOST 有回應了，說是把網路卡換了，可以連了，先看看穩定的情形再說吧
