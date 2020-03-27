+++
title = "換成 Plone"
date = 2004-12-03T18:19:00Z
updated = 2007-11-05T06:42:54Z
tags = ["Python", "Zope"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<br /><h1>我先自首</h1><br />我實在是太善變了，原本用 <a href="http://coreblog.org/">COREBlog</a> 的系統才沒有一個星期，我就不滿意她的擴充性，也覺功能不多(但是夠用)，自己非常的貪心，又看到使用 <a href="http://www.zope.org/">Zope</a> 及 <a href="http://www.plone.org/">Plone</a> 相當有經驗的 <a href="http://blog.tcchou.org/">TCC</a> 前輩網站後，在參考前輩網站的詳細解說及範本後，在電腦螢幕前奮戰幾天，現在新的架構誕生，是架構於 Plone 上的，也作了些許的修改，修了一些在Plone 上 Default Page Template 的蟲，也發現一些，再學 <a href="http://blog.tcchou.org">TCC</a> 前輩的網頁 <a href="http://blog.tcchou.org/dict/index">Index</a> 接下來有時間要記得寫一篇有關這些的客制化的細節，免得自己會忘記，現在大概剩下 "搥背" 的功能要再想想辦法了。<br /><br />目前可以用 <a href="http://sukima.ddo.jp/Plone/Members/yusei/Download/">CMFTrackback</a> ，不過要作修改才可以在 Plone 2 上使用。<br /><h1>先簡述有那些修改</h1><br />大約有<br /><ul><br />	<li>discussion_reply</li><br />	<li>discussion_reply_form</li><br />	<li>discussionitem_view</li><br />	<li>viewThreadsAtBottom</li><br /></ul><br />自己加的<br /><ul><br />	<li>portlet_recentreply</li><br />	<li>portlet_static</li><br />	<li>ploneCustom.css</li><br />	<li>base_properties</li><br />	<li>script，for recatalog discussion item，解決 Discussion Item, 在 Clear Catalog 後重建，後找不到的問題</li><br />	<li>script，for 導覽欄下面的 "索引"</li><br />	<li>重建 portal_catalog 下的  plone_lexicon 換成用 <a href="http://www.zope.org/Members/panjunyong/CJKSplitter">CJKSplitter</a></li><br />	<li>小改一下 Products/CMFDefault/Document.py，4 ~ 8 lines</li><br />	<li>小改一下 DateTime/DateTime.py，1 line</li><br />	<li><a href="http://www.debian.org">Debian</a>，<a href="http://www.zope.org/">Zope 2.7.2</a>，"<a href="http://www.plone.org/">Plone 2.0.5</a>，<a href="http://plone.org/documentation/archetypes">Archetypes 1.3.1-final</a>，<a href="http://www.zope.org/Members/panjunyong/CJKSplitter">CJKSplitter</a></li><br /></ul>
