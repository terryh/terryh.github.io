+++
title = "Zope 下的內容管理系統"
date = 2005-11-11T01:21:00Z
updated = 2007-11-06T09:25:06Z
tags = ["Python", "Plone", "Zope"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<br /><h1>CMS (Content Management System)</h1><br /><a href="http://www.zope.org/">Zope</a> 一用好幾年了，現在已經有好幾套內容管理系統可用，有時會讓很多人不知道如何選用<br /><br />Zope 的 CMS 大多是基於 <a href="http://www.zope.org/Products/CMF/">CMF</a> 的框架上，再繼續發展，所以有一定的相依性，不過這是好也是不好，Zope 和 CMF 是不同的專案，這樣增加了彈性，不過卻也讓新版的 CMF 永遠必須比  Zope 慢，像這一次 Zope3 是比較大的改版，CMF 要好一陣子才能跟上來，對專案的開發不利，比如說你的專案是相依在 CMF 上，那就算是 <a href="http://www.zope.org/Products/Zope3">Zope3</a> 出來了，你可能還要苦等 CMF Zope3 的版本很久，如果您的專案是相依 CMF 及 Plone 的話，那你可能要等更久，這都是讓開發人員不喜歡的，可能以前作過的都要重新作了。就像是 Zope3 出來到現在，不知道要多久，她的 Product 及成熟度才可以和 Zope2 相同。<br /><br />好吧開始說 CMS　了<br /><br /><a href="http://plone.org/">Plone</a> 算是在台灣最有名的，不過從 2.1 的版本後，他的內容就都是用 Archetype 了，不再是 CMF 的內容元件了，也就是說以後相依性，要加 Archetype ，而且在升級時，如果自己裝了很多的產品，或是客製太多的內容，都會造成一定的難度，要自己 patch 升級的程式，這對不是開發人員的使用者來說是個難題。<br /><br /><a href="http://www.cps-project.org/">CPS</a>　網頁的內管理系統，架構於 Zope 與 CMF 上，適合於內容網站，或是企業內部或是外部的站台<br /><br /><a href="http://www.infrae.com/products/silva">Silva</a> 也是一個內容管理系統，內容均以 XML 的格式儲存<br /><br />CPS 和 Silva 應該都是基於 CMF 比較多的，但是目前中文的支援都比較不好<br /><h1>感言</h1><br />效能還是蠻重要的，好像目前在大型的站台的運用，除了 Cache 還是 Cache，這對一些個人化的服務是一個缺點，一旦沒有太多的經費加伺服器，然後線上人數很多時，在沒有 Cache 的狀態，反應時間有一點點難過。<br /><br />Zope 的發展，到了 Zope3 真的是變很多，如果各家 CMS 的產品也都可以共用不知道有多好，要是可以集合各家的專長和力量，一定可以做出更可怕的東西。<br /><br />不過以 Plone 為基礎來開發，已經是很強的系統了，讓使用者有很多不同的體驗，也有許多其他的架構所沒有的優勢及彈性，在介面上 web，webdav，ftp，plonedesktop 還有 external editor 都是很好用的，這樣的內容管理系統也是很夠用了，不過還是希望可以再進步。
