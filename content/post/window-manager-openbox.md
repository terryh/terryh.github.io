+++
title = "window manager openbox"
date = 2010-08-01T20:39:00Z
updated = 2010-08-02T06:44:16Z
tags = ["GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

跟大家使用得來比，算是一種很冷門的的 window manager<br />如果要取代 gnome 預設的<br /><br />terry@terry:~$ cat .gnomerc <br /><code><br />export WINDOW_MANAGER=openbox<br /><br />terry@terry:~$ <br /></code><br /><br /><br />預設的 keybind 不夠的話，可以自訂<br /><br /><br /><a href="http://openbox.org/wiki/Help:Bindings">http://openbox.org/wiki/Help:Bindings</a><br /><br />例如視窗最大，還有最小<br />用 vim 編輯，這一個檔案<br />terry@terry:~$ vim ~/.config/openbox/rc.xml<br />在  <keyboard> 的 xml 標籤裡加入<br /><code><br /><br />&lt;keybind key="A-F9"&gt;<br />   &lt;action name="Iconify"&gt;<br />    &lt;/action&gt;<br />&lt;/keybind&gt;<br />&lt;keybind key="A-F10"&gt;<br />    &lt;action name="MaximizeFull"&gt;<br />    &lt;/action&gt;<br />&lt;/keybind&gt;<br /><br /><br /></code>
