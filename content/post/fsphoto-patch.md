+++
title = "FSPhoto patch"
date = 2005-07-01T03:31:00Z
updated = 2007-11-05T06:45:00Z
tags = ["Zope"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<p>話說前一陣子用了 <a href="fsphoto">FSPhoto</a> ，後來發現不能用 FTP 的方式上傳，有點美中不足，所以又激起了找 bug 的鬥志，嗯，這是新舊 diff 的內容，請慢用，真的好短，不過我追了很久，真是太遜了。 </p><br /><p>相信在新版的 Plone 2.1 中，或是 Archetypes 1.3.4 會有更好的方法。</p><br /><p>還有要在 <a href="http://www.sourceforge.net">SourceForge</a> 上登記 bug 或是 submit patch 時，明明已經登入了，總還是會變成 nobody，疑惑中。</p><br /><p>這是 diff 的內容，FSPhoto_New 的內容是新的:<br /><pre><br />   Common subdirectories: FSPhoto/Extensions and FSPhoto_New/Extensions<br />   diff FSPhoto/FSImage.py FSPhoto_New/FSImage.py<br />   11a12<br />   &gt; from Products.Archetypes.Marshall import PrimaryFieldMarshaller<br />   36a38<br />   &gt;                  primary=1,<br />   41c43<br />   &lt;     ))<br />   ---<br />   &gt;     ),marshall=PrimaryFieldMarshaller())<br />   diff FSPhoto/FSPhoto.py FSPhoto_New/FSPhoto.py<br />   10a11<br />   &gt; from Products.Archetypes.Marshall import PrimaryFieldMarshaller<br />   27a29<br />   &gt;                      primary=1,<br />   36c38<br />   &lt;         ))<br />   ---<br />   &gt;         ),marshall=PrimaryFieldMarshaller())<br />   diff FSPhoto/FSPhotoAlbum.py FSPhoto_New/FSPhotoAlbum.py<br />   16a17<br />   &gt; from Acquisition import aq_base<br />   Common subdirectories: FSPhoto/docs and FSPhoto_New/docs<br />   Common subdirectories: FSPhoto/skins and FSPhoto_New/skins<br /></pre><br /></p>
