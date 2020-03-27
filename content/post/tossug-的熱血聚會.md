+++
title = "TOSSUG 的熱血聚會"
date = 2005-09-02T19:12:00Z
updated = 2007-11-06T09:24:57Z
tags = ["新聞", "生活雜記"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

每個星期二，在台大的迴廊咖啡，都會有熱血的聚會，這一次是由 pake 主講 Plone<br /><br />非常的精采，也聽到了其他幾位社群朋友的分享，很有收穫。<br /><br />以後要是有其他的議題，應該也要參加才是<br /><br />在談話中，葉平大哥，說想要有在 Plone 中有個群組的工作區，可以讓大家加入新的資料，自己只可以編修自己的，不能修改別人的，但是都有看的權限。<br /><br />一開始，我覺得也許可以在 Plone 的 work flow 中解決，不過 Ping 想要直接新增就可以，不經過變化工作流程的改變狀態的方式，我說要再研究研究。<br /><br />回家以後實際試的結果是，加入群組後，將群組工作資料夾的 <code>local roles</code> 的預設對應刪除，然後進入群組工作資料夾 <code>Security</code> 的管理介面，將 <code>add portal content</code> 的 Acquire 取消選取，改選取 <code>Manager</code>，<code>Member</code>，不要選 <code>Owner</code>，然後看一下 <code>Modify portal content</code> 是不是也是取消選取 <code>Acquire</code> 而只勾 <code>Manager</code> 及 <code>Owner</code>，基本上這樣就可以達到葉大哥的需求了，不知道會不會太複雜。<br /><br />這樣的做法，變成只要是 Member 都可以在這個資料夾新增，要做到，完全只有 Group member 可以的話，應該只是新增一個 Role，然後設成這個 Role 可以新增，不能修改，只有 Owner 可以修改，然後原本的 local roles mapping 就指到這個 Role 應該也可以。<br /><h1>相關的連結</h1><br /><a href="http://tossug.blogspot.com/2005/08/plone.html">http://tossug.blogspot.com/2005/08/plone.html</a><br /><br /><a href="http://tossug.blogspot.com/2005/08/podcast-for-tossug-plone.html">http://tossug.blogspot.com/2005/08/podcast-for-tossug-plone.html</a>
