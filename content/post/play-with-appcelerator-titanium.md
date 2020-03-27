+++
title = "Play with Appcelerator Titanium"
date = 2011-04-08T23:08:00Z
updated = 2011-04-09T00:18:52Z
tags = ["PhoneGap", "Titanium"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="http://developer.appcelerator.com/assets/img/DEV_titmobile_image.png" alt="Titanium" /><br /><br />體驗一下， cross platform mobile app 的開發工具 Appcelerator Titanium<br /><br /><a href="http://developer.appcelerator.com/">Appcelerator Titanium</a><br /><br />在 Debian testing 下面，會有一點點小問題，可以這樣解，分享的連結檔，有一些相依性的問題<br /><br /><a href="http://developer.appcelerator.com/question/14471/symbol-lookup-error-usrliblibgdk-x11-20so0-undefined-symbol-gmallocn-solved">http://developer.appcelerator.com/question/14471/symbol-lookup-error-usrliblibgdk-x11-20so0-undefined-symbol-gmallocn-solved</a><br /><br /><br />DUMMY STEP<br /><br />1. download <a href="http://www.appcelerator.com/products/download/">http://www.appcelerator.com/products/download/</a> ， for me is 64bit Linux <a href="http://www.appcelerator.com/download-linux64">http://www.appcelerator.com/download-linux64</a><br /><br />2. tar zxvf Titanium Developer-1.2.2 ; cd Titanium\ Developer-1.2.2/ ; ./Titanium\ Developer # will auto download SDK<br /><br />3. git clone https://github.com/appcelerator/KitchenSink.git <br /><br />3. ./Titanium\ Developer # import project KitchenSink<br /><br />4. now you can build this app to your emulator or device<br /><br />PS1: 也有 <a href="http://www.phonegap.com/">PhoneGap</a> 可以玩，都很容易上手，還有 Andriod SDK ，或是 IOS 的 SDK 是一定要裝得啦， Mac OS 可以放在 VirtualBox 裡面跑<br /><br />PS2: 如果要真的要 mobile development 也可以，把 ~/.titanium/ ，及整個 Titanium\ Developer-1.2.2 資料夾都放 Dropbox，再用 symbolic link 的方式連 ~/.titanium ，所以只要有無敵的 editor 就可以了<br /><br />PS3: 真的不喜歡 GUI ， 要用 command line <a href="http://guilherme.pro/2011/04/06/titanium-mobile-hack-execute-your-projects-from-the-command-line-using-make/">http://guilherme.pro/2011/04/06/titanium-mobile-hack-execute-your-projects-from-the-command-line-using-make/</a> ，他的 test project 也蠻酷的 <a href="https://github.com/guilhermechapiewski/titanium-jasmine">https://github.com/guilhermechapiewski/titanium-jasmine</a>
