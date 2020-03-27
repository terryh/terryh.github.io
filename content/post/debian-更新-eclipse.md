+++
title = "Debian 更新 Eclipse"
date = 2012-07-11T19:06:00Z
updated = 2012-07-11T19:09:48Z
tags = ["Debian", "Eclipse"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

用 Debian testing 的人，最近應該都會更新到 Eclipse 3.8 版本  <br /><br />testing 上面的 eclipse-cdt 的套件不夠新，會少一些東西 Android Development Kit 更新到 r20 會報  套件相依的問題 <br /><br /><pre>Cannot complete the install because one or more required items could not be found.<br />  Software being installed: Android Native Development Tools 20.0.0.v201206242043-391819 (com.android.ide.eclipse.ndk.feature.group 20.0.0.v201206242043-391819)<br />  Missing requirement: Android Native Development Tools 20.0.0.v201206242043-391819 (com.android.ide.eclipse.ndk.feature.group 20.0.0.v201206242043-391819) requires 'org.eclipse.cdt.feature.group 0.0.0' but it could not be found<br /></pre><br />解決方式紀錄一下  <br /><br />先不要用 debian 自帶的 eclipse-cdt  <br /><br />更新 Android 開發套件的時候，先安裝，新版的 cdt 到  加兩個 software update 的路徑<br /><br />名稱可以自己取  <br /><br />Window - Preference - Install/Update - Availiable Software  <br /><br />安裝 CDT <br />http://download.eclipse.org/tools/cdt/releases/juno  <br /><br /><br />安裝 Eclipse 更新列表下 Web, XML, Java EE and OSGi Enterprise Development 下面的 WST Server Adapters. 套件 <br />http://download.eclipse.org/releases/juno/   <br /><br /><br />都裝完以後，就可以裝新版的 Android Development Kit 了<br /><br />
