+++
title = "golang crawler demo (go routine)"
date = 2018-03-06T00:26:00Z
updated = 2018-03-06T00:26:17Z
tags = ["Golang"]
draft = true
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

golang crawler demo<br />我從一開始的 go routine 好了，首先要要我們自己要了解，go routine 的優缺點，適合的情境，再加以套用進去，<br />重複驗證，是否，有如自己想的那樣，帶來益處。<br /><br />首先，我先分析一下，做一下功課，簡單筆記一下 go rountine 的優缺點<br /><br />優點<br /><br />1) 簡單易用, go something() 去吧，就可以，語意上也容易理解，需要需要做資料的連結，通常搭配 channel 合用<br />2) 效能優異 (這一點需要自己驗證一下，網路上面看到的，就是他的情境是很理想的情形下)<br />3) 由 go 自己的 scheduler 自己去調度，不是 os threading 的方式，相對沒有這麼佔用系統資源<br /><br /><br />缺點<br />1) 天下沒有白吃的午餐 small overhead <a href="https://medium.com/@robot_dreams/goroutines-and-channels-arent-free-a8684f3b6560">https://medium.com/@robot_dreams/goroutines-and-channels-arent-free-a8684f3b6560</a><br />1) 和所有多線程程式ㄧ樣，都要處理，共享資料的部分 (嚴格來說不算缺點，比較像是歷史共業)<br /><br /><br />以上是分析完的結果，進入實作，由於，高<br /><br /><br />
