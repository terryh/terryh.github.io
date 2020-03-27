+++
title = "automan open source"
date = 2010-11-14T00:20:00Z
updated = 2012-04-01T20:13:25Z
tags = ["wxPython", "Python", "程式交易", "AutoMan"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

AutoMan 是前些時候寫得 <a href="http://www.blogger.com/2010/01/automan.html">AutoMan 康合日盛下單機測試版</a>，自己有需要開發的圖形介面下單機，一開始，看看好像大家都收錢，就也跟著大家的規矩，定一個小小的收費門檻，讓想要做程式交易的人，心裡有個底，但是後來自己心境的轉換，也算是改變吧，工具只是，開始而已，後面難的是風險的控管（心的控管），及交易策略的開發與執行，一直以來，除了停電，網路斷，還有報價源，報價錯誤，這些反而比較不不穩地外，automan 都很稱職，我先 Eating my own dog food 的原則，用了很久了，不過醜話還是要先說，工具，只是開始，是幫你，還是害你，誰也不知道，自己才是主人，賺了，記得多幫助別人，錢賺來是要花的，輸了，不要怪東怪西，怪天怪地，怪政府<br /><br />各位，要是有好的建議或是程式的 patch 請不吝賜教，程式非常的短<br /><br />專案網頁 <a href="https://github.com/terryh/automan">https://github.com/terryh/automan</a>，說明也可以在專案頁看到<br /><br />目前，有 2014 12 月的期限，只要改一下，重新編譯就幾乎沒限制了，有期限，是希望，有更新的話，大家可以重新下載，不要有錯誤(bug)，找到修正後，大家還是傻傻的舊版一直用<br /><br /><span style="font-size: x-large;">更新紀錄</span><br /><br />0.4BETA 增加程式圖示，有好心人士可以回報一下在 64 bit 的 windows 環境下可不可以，還是需要另外建構，這一個檔案，用 PyInstaller + Python2.7.2 在 windows XP 32bit 的環境建構，第一次執行會產生 COM 的紀錄檔，先前都是用 Python2.5 + py2exe 在 32bit 環境建構，期限 201412，發佈時間2012/04/01<br /><br /><a href="http://dl.dropbox.com/u/14137697/20120401/automan.exe">http://dl.dropbox.com/u/14137697/20120401/automan.exe</a><br /><br />0.4BETA，期限 201412，發佈時間 2012/03/29<br />支援康和 OCX v3 的 API，移除支援舊版本康和 API，因為他們不支援了，訂正康和的代碼提示<br /><a href="http://dl.dropbox.com/u/14137697/20120329/automan.exe">http://dl.dropbox.com/u/14137697/20120329/automan.exe</a><br /><br />0.3BETA，期限 201312<br />有支援康和 OCX v2 的 API<br /><a href="http://dl.dropbox.com/u/14137697/20110608/automan.exe">http://dl.dropbox.com/u/14137697/20110608/automan.exe</a><br /><br />0.2BETA，期限 201212 <br /><a href="http://dl.dropbox.com/u/14137697/automan.exe">http://dl.dropbox.com/u/14137697/automan.exe</a><br /><br />在 windows XP 上，同時需要 MSVCR71.DLL 及 MSVCP71.DLL 請自行下載，如果是Windows XP可放在 C:/WINDOWS/SYSTEM32/ 下面即可，或是存到程式執行目錄<br /><br /><a href="http://www.dll-files.com/dllindex/dll-files.shtml?msvcp71">http://www.dll-files.com/dllindex/dll-files.shtml?msvcp71</a><br /><br /><a href="http://www.dll-files.com/dllindex/dll-files.shtml?msvcr71">http://www.dll-files.com/dllindex/dll-files.shtml?msvcr71</a><br /><br /><br />PS: 有認真的慢慢在做，像 TS 的工具，有機會，在發表給大家用，不過自從開始作遊戲之後，這一個順序，排在做遊戲之後 ;-)，到了遊戲公司後，遇見幾個有趣的人，做遊戲真的很好玩耶，以前都覺得玩遊戲很浪費生命
