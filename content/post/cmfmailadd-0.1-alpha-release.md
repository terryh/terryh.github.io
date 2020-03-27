+++
title = "CMFMailadd 0.1 Alpha Release"
date = 2005-04-28T08:39:00Z
updated = 2007-11-05T06:43:52Z
tags = ["Zope"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<br /><h1><a href="http://www.zope.org/Members/terryh/Packages">CMFMailadd</a> 出生了</h1><br />在網路上一直找不到和 <a href="http://www.coreblog.org/">COREBlog</a> 一樣可以 Moblog 的功能，來讓 Plone 用，只好自己花一些時間自己生嘍！ 主要的一隻程式才 336 行，不知道這麼短的程式，我同時會生多少 bugs，有興趣的人就用用看吧！ 說實在，CMFMailadd 又讓我的懶人 blog 向前邁一步，除了可以用傳統瀏覽器，ftp，或是 webdav 的方式加入新內容，現在也可以用 Email 的方式了，尤其是有些手機已經可以直接發 email，雖然手機上沒有 Emacs 或是 Vim，不過也不失為一個克難的方法，真是 "科技始終來自於人性"，我真是夠懶了。 :o)<br /><br />這個工具完全是以方便性大於安全性作考量，用來收信的 pop3 帳號，最好不要給 shell 的權限。<br /><h1>主要功能</h1><br />您可以設定一個 pop3 帳號來讓 CMFMailadd 收信，如果寄件者的郵件地址，是會員的郵件地址，同時該地址也在 CMFMailadd 容許的郵件地址清單中，那麼這一封信的內容就會用 CMFMailadd 的預設型態加入該郵件地址對照的會員資料夾中，或是依照設定的資料夾，不會自動轉換郵件和網站的字元編碼，也不會判斷重複附加檔案的名字。<br /><h1>使用方法：</h1><br />將 CMFMailadd 放到您 <a href="http://www.zope.org">Zope</a> 的 Products 資料夾下，解壓縮，重新啟動 Zope，在到您 <a href="http://www.plone.org">Plone</a> 的設定介面下，選 "新增/移除產品"， 就可以看到 CMFMailadd 可以點選安裝了，安裝後，用 Zope 的管理介面看，在您的 Plone Site 的根目錄下，有一個叫 portal_mailadd 的工具，設定一下 property 就可以了，這一個工具下，有一個 recieve 的 method 可以去收信，完整的 url 可以點一下 Overview 那一項，下面有寫，可以用排程的工具去執行，像是設定 cron job 的方式，去觸發執行這一個 URL。<br /><br />用 wget 去觸發的 example:<br /><pre><br />     wget --http-user=username --http-passwd=password http://localhost/Plone_Site/portal_mailadd/receive</pre><br />property 說明<br /><ul><br />	<li>folder: 資料夾的名稱，這樣信件的本體就會加到寄件者會員的家目錄下的folder，空白代表直接加入家目錄</li><br />	<li>file_folder: 附件資料夾的名稱，這樣信件的附件就會加到寄件者會員的家目錄下的 file_folder，空白就加入家目錄</li><br />	<li>default_content_type: 預設的資料型態 (Document 或是 News Item)</li><br />	<li>mailadd_host: POP3 帳號的主機名稱或是位址</li><br />	<li>mailadd_user: POP3 登入帳號名稱</li><br />	<li>mailadd_passwd: POP3 帳號密碼</li><br />	<li>mailadd_email_addr: 加入可以寄信的郵件地址，請用英文逗點隔開一個以上的地址 ","</li><br />	<li>workflow_action: 預設郵件加入後的狀態，也就是 Plone 中的流程(workflow),如 submit, reject, publish ....</li><br />	<li>body_separater: .....</li><br /></ul><br /><h1>備註</h1><br /><ul><br />	<li>我的測試環境是在 Zope 2.7.5，Plone 2.0.5</li><br /></ul>
