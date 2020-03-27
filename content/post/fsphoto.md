+++
title = "FSPhoto"
date = 2005-05-23T08:45:00Z
updated = 2007-11-05T06:44:30Z
tags = ["Python", "Plone", "Zope"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<br /><h1>簡單的 <a href="http://sourceforge.net/project/showfiles.php?group_id=55262&amp;package_id=123821">FSPhoto</a></h1><br />架構相單精簡，也沒有太多的功能，沒有像 <a href="http://www.zphotoslides.org/">ZPhotoSlides</a> 那樣有許多的功能，但是可以將圖片放在檔案系統上，不會讓您的 ZODB 一下就佔用很大的空間，最重要的是，圖片可以全用 <a href="http://www.apache.org">Apache</a> 來處理，減輕 <a href="http://www.zope.org">Zope</a> 的負擔，也不失為一個簡易又輕便的解決方法。<br /><h1>注意事項：</h1><br />如果是用較新的 <a href="http://plone.org/documentation/archetypes/">Archetypes</a> ，請將 FSPhoto 套件中，FSImageField.py 檔案中的 has_pil 改成 HAS_PIL，在檔案系統建立 /var/www/photos 這一個目錄，再將目錄的擁有者改成 Zope 的程式執行者，再來要用 Apache 來送檔案的話，就在 Apache 的設定檔中用 Rewrite Rule 來設定就可以了。<br /><h1>相關資料：</h1><br /><a href="http://sourceforge.net/projects/collective/">CMFPhoto</a><br /><br /><a href="http://sourceforge.net/projects/collective/">CMFPhotoAlbum</a><br /><br /><a href="http://sourceforge.net/projects/collective/">PloneRealtyAlbum</a><br /><br /><a href="http://sourceforge.net/projects/collective/">FSPhoto</a><br /><br /><a href="http://www.zphotoslides.org/">ZPhotoSlides</a>
