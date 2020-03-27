+++
title = "Yosemite 的痛"
date = 2014-10-29T17:43:00Z
updated = 2014-11-06T05:51:49Z
tags = ["Mac"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

我想 Mac Yosemite 的痛，大家漸漸感受到了<br /><br />這裏有一篇，有關無線網路爛了的解法，有問題的朋友可以試試，我的 WL-330nul 一樣是沒有用，只能用斷斷續續的 Ap 模式 <br />感覺回到了用 Linux 時的初衷，還會邊拔插裝置，tail -f 看一下 /var/log/system.log 的錯誤<br /><br /><a href="http://osxdaily.com/2014/10/25/fix-wi-fi-problems-os-x-yosemite/">http://osxdaily.com/2014/10/25/fix-wi-fi-problems-os-x-yosemite/</a><br /><br />還有一種方法，就是把藍芽關掉，再試試看<br /><br />另外，Yosemite 已經預設不讓你裝沒有簽證過的 kernel module 了，所以用 homebrew 要裝 osxfuse 會吐<br /><pre><code class="language-markup"><br />terry@localhost /var/log $ brew install osxfuse<br />osxfuse: osxfuse is already installed from the binary distribution and<br />conflicts with this formula.<br />osxfuse: OS X Mavericks or older is required for this package.<br />OS X Yosemite introduced a strict unsigned kext ban which breaks this package.<br />You should remove this package from your system and attempt to find upstream<br />binaries to use instead.<br />Error: Unsatisified requirements failed this build.<br /><br /></code><br /></pre><br />我是直接下載 dmg 安裝了
