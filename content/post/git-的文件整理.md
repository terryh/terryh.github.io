+++
title = "git 的文件整理"
date = 2010-09-15T08:08:00Z
updated = 2010-12-12T20:41:14Z
tags = ["Doc", "Git"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="http://lh4.ggpht.com/_Bsjm2Qp0Duc/TJDZUCrLnKI/AAAAAAAABB4/8xNP3Kf6zGo/s800/200px-Icon-notepad.svg.png" /><br /><br />install gitosis，要有自己的 git server 的話，覺得自己程式寫得太差，不好意思放到 github 的話 ;-)<br /><br /><a href="http://www.hackido.com/2010/01/installing-git-on-server-ubuntu-or.html">http://www.hackido.com/2010/01/installing-git-on-server-ubuntu-or.html</a><br /><br /><a href="http://scie.nti.st/2007/11/14/hosting-git-repositories-the-easy-and-secure-way">http://scie.nti.st/2007/11/14/hosting-git-repositories-the-easy-and-secure-way</a><br /><br />windows 上的 GUI 的工具<br /><br /><a href="http://code.google.com/p/tortoisegit">http://code.google.com/p/tortoisegit/</a>  <br />並需先裝  <a href="http://code.google.com/p/msysgit/">http://code.google.com/p/msysgit/</a><br /><br />windows 用安裝完後記得用，GitBash<br /><br />ssh-keygen -C "yourname" -t rsa<br /><br />接著就可以把 publich key  放到 C:\Documents and Settings/YOR NAME/.ssh/id_rsa.pub<br /><br /><br />有關 hudson 整合<br /><br /><a href="http://wiki.hudson-ci.org/display/HUDSON/Plugins">http://wiki.hudson-ci.org/display/HUDSON/Plugins</a><br /><br />參考資料<br /><br />Git Cheat Sheet <a href="http://ktown.kde.org/~zrusin/git/git-cheat-sheet.svg">http://ktown.kde.org/~zrusin/git/git-cheat-sheet.svg</a><br /><br /><a href="http://github.com/guides/git-cheat-sheet">http://github.com/guides/git-cheat-sheet</a><br /><a href="http://progit.org/">http://progit.org/</a><br /><a href="http://progit.org/book/zh/">http://progit.org/book/zh/</a> 中文版<br /><br />Git from subversion<br /><br /><a href="http://www.ibm.com/developerworks/linux/library/l-git-subversion-1/">http://www.ibm.com/developerworks/linux/library/l-git-subversion-1/</a><br /><a href="http://www.ibm.com/developerworks/linux/library/l-git-subversion-2/">http://www.ibm.com/developerworks/linux/library/l-git-subversion-2/</a><br /><br /><a href="http://git.or.cz/course/svn.html">http://git.or.cz/course/svn.html</a><br /><br /><a href="http://plog.longwin.com.tw/my_note-unix/2009/05/19/git-learn-initial-command-2009">http://plog.longwin.com.tw/my_note-unix/2009/05/19/git-learn-initial-command-2009</a><br /><br />Git with SVN<br /><a href="http://blog.kanru.info/archives/466">http://blog.kanru.info/archives/466</a><br /><br />Linux Talks at Google<br /><br />(影片有點長，我也沒有時間看，很閒的人可以看)

{{< youtube 4XpnKHJAok8 >}}

ps: 半年前試著將公司的版本控制由 subversion 轉移到 git 上面，遇到的問題大多是，同事不能接受，太常 conflict ，需要 merge ，沒有像 subversion 那樣，直接 update ，或是在 windows 上有 gui 的 merge tool 可以用，我 windows 也沒有很熟，搞不太清楚 windows 上設定好 merge tool，我都是用  vimdiff，所以後來，同事就全部繼續用 subversion ，比較歡樂，簡單，所以有一些文件整理一下，希望對有需要的人有幫助，我則是都用 git svn fetch, git svn rebase, git svn dcommit 來與 subversion server 溝通，同事們則是用，VPN 連到公司，似乎這樣也夠他們用了，畢竟，用過 git 的好，真的很難回去啦
