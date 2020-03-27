+++
title = "Solr with django-haystack"
date = 2011-03-16T08:11:00Z
updated = 2011-03-16T08:42:28Z
tags = ["Solr", "Apache", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://lucene.apache.org/solr/">Solr</a> 和 <a href="http://haystacksearch.org/">django-haystack</a> 的組合，真是強大，全文檢索真是太優了，交給專業的就是沒錯，多得是一大堆東西，還要自己蠻幹<br /><br /><br />這樣可以解決，用 RealTimeSearchIndex 的 ManyToManyField 不更新的問題，不過變成更新資料重複 update Solr ，的 over head ，以後，應該有更好的做好<br /><br />Google Group 的討論 <a href="http://groups.google.com/group/django-haystack/browse_thread/thread/a274b5aeb121b1d4/5f4c4f7632aa1dfc?pli=1">http://groups.google.com/group/django-haystack/browse_thread/thread/a274b5aeb121b1d4/5f4c4f7632aa1dfc?pli=1</a><br /><br /><script src="https://gist.github.com/872626.js?file=models_and_search_indexes.py"></script><br /><br /><br />PS: 為什麼 Solr 而不是 <a href="http://xapian.org/">Xapian</a> 或是直接用 <a href="http://sphinxsearch.com/">Sphinx</a> ，考量原因是 Apache 及 GPL license 還有就是成熟度，及 Solr 提供 API ，算是一個很方便 Lucene 接口，不單可以只做資料庫的全文檢索，可以應用的範圍相當大，這就給大家自由發揮了
