+++
title = "screen"
date = 2012-01-05T22:19:00Z
updated = 2012-01-06T07:18:30Z
tags = ["Debian", "GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

改一下 ~/.bashrc<br /><br /><br /><pre>GITPS1='$(__git_ps1 " (%s)")'<br /><br />case "$TERM" in<br />xterm*|rxvt*)<br /><br />    PS1="${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]${GITPS1}\$ "<br />    PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"<br />    ;;<br />screen*)<br />    PS1="${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]${GITPS1}\$ "<br />    PATHTITLE='\[\ek\W\e\\\]'<br />    # Use program name as title<br />    PROGRAMTITLE='\[\ek\e\\\]'<br />    PS1="${PROGRAMTITLE}${PATHTITLE}${PS1}"<br />    ;;<br />*)<br />    ;;<br />esac<br /><br /></pre><br />小抄一下別人的 ~/.screenrc<br /><br /><pre># Caption line<br />#caption always "%{= R}[ %{=b b}%-w%{=rb db}%>%n %t%{-}%+w%{-b}%< %=%{R}][%{M} %Y-%m-%d %{G}%c%{R}]"<br />caption always "%{=b k}%{b y} %m-%d %c / %{k}%L=%-w%7>%{g}%n %t%{-}%+w%-014< %-016=%{c} %l "<br /><br /><br /># Set default encoding using utf8<br />defutf8 on<br /><br /># Refresh the display when exiting programs<br />altscreen on<br /><br /># Dynamic title<br />shelltitle '$ |bash'<br /><br /># Set xterm's title<br />hardstatus string "screen: %t"<br /><br /># C-a b --(switch to)--> view big5 data<br />bind b encoding big5 utf8<br /># C-a u --(switch to)--> view utf8 data<br />bind u encoding utf8 utf8<br /><br /></pre><br />參考<br /><br /><a href="http://adam8157.info/blog/2010/05/terminal-bash-screen/">http://adam8157.info/blog/2010/05/terminal-bash-screen/</a><br /><br /><a href="http://archerworks.blogspot.com/2010/05/linuxscreenbindkey.html">http://archerworks.blogspot.com/2010/05/linuxscreenbindkey.html</a><br /><br />這樣，顏色，還有訊息都豐富了，不會逛到哪一台主機 git 到哪一個 branch 都分不出來
