+++
title = "暫時性的 flashplayer on Deban AMD64"
date = 2010-08-04T00:32:00Z
updated = 2010-08-04T00:47:43Z
tags = ["Debian", "FlashPlayer", "GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

有鑑於，現在很多的遊戲，還是要用 flash 玩，還有 HTML5 看 youtube 還是很慢，iceweasel 還不行，要 Google Chrome， 所以 HTML5 各個瀏覽器的支援沒有到位， web flash 遊戲也沒有比較好的解決方案，所以只好繼續用 flash <br /><br />可以參考 Debian WIKI page<br /><br /><a href="http://wiki.debian.org/FlashPlayer#DebianTesting.27Squeeze.27amd64">http://wiki.debian.org/FlashPlayer#DebianTesting.27Squeeze.27amd64</a><br /><br />If you're on Debian testing<br /><code><br />apt-get install fakeroot binutils nspluginwrapper ia32-libs ia32-libs-libidn11 ia32-libs-libssh2 ia32-libs-libcurl3 ia32-libs-libnspr4 ia32-libs-libnss3<br /></code><br /><br />download <a href="http://people.debian.org/~bartm/flashplugin-nonfree/flashplugin-nonfree_10.1.53.64.1_amd64.deb">http://people.debian.org/~bartm/flashplugin-nonfree/flashplugin-nonfree_10.1.53.64.1_amd64.deb</a><br /><br /><code><br />dpkg -i flashplugin-nonfree_10.1.53.64.1_amd64.deb<br /></code><br /><br />restart iceweasel, or Google Chrome, you should be able have flashplayer under your browser ;-)<br /><br />Off course， Thanks a lot to bartm for prebuild package
