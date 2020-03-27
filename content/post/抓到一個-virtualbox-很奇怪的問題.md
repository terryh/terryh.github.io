+++
title = "抓到一個 VirtualBox 很奇怪的問題"
date = 2011-02-26T23:10:00Z
updated = 2011-02-26T23:21:41Z
tags = ["VirtualBox", "程式交易"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

心血來潮，測試一些交易策略，把 TS 下的作好的測試要移到 HTS 後，發現點了 4000 程式語言的功能，居然整個 windows 當住了，我的交易環境，一直都是放在 VirtualBox 裡的 windows 跑得，找到最後居然是，最近， Debian 更新到新版的 VirtualBox 4.0.2 後， Guest OS 也跟著裝 4.0.2 的 <br /><br />VBoxGuestAdditions_4.0.2.iso 這個就是重點，詳細禍首，是 VBoxGuestAdditions 還是 HTS 我也不是很確定(當然 HTS 有問題的機會很大，依歷史經驗來說)，但是確實可以把 windows 搞掛，所以 GuestAdditions 還是保守一點，裝 3 系列的就很穩了<br /><br /><a href="http://download.virtualbox.org/virtualbox/">http://download.virtualbox.org/virtualbox/</a>
