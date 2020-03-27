+++
title = "HTS bug 滿天飛"
date = 2009-06-06T05:02:00Z
updated = 2009-06-12T15:10:27Z
tags = ["財經", "新聞", "程式交易"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

市場上有很多的朋友熱衷程式交易，現在國內市場的工具，很多人選的是HTS<br />他的門檻低，算是非常容易上手，不過，有很多的內建函式，不一定可以正確執行<br /><br />有時候在 TS(tradestation) 裡頭可以用的，在HTS裡不一定就正確<br /><br />如果有用到指標的部份，一定要再三確認，是相同的數據，免得TS回測起來很漂亮，完美的45度線，結果，實際到了HTS跑，印鈔機變成了碎鈔機<br /><br />目前，我有用到的發現，HTS內建函式和 TS 不一樣的有<br /><br />在 HTS 裡不能這樣用<br /><br />Highest(X-Y,Length)<br /><br />Lowest(X-Y,Length)<br /><br />IFF() 和 TS 不一樣<br /><br />StdDev()也和 TS 不一樣<br /><br />所以，要另外寫函式解決，如果還是要用 HTS 下單的話
