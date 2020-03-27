+++
title = "PyAMF django test client"
date = 2010-09-07T02:50:00Z
updated = 2010-09-10T20:28:21Z
tags = ["Python", "PyAMF", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="http://pyamf.org/"><img src="http://lh6.ggpht.com/_Bsjm2Qp0Duc/TIrwW3IcLmI/AAAAAAAAA-Q/7OWkMUA3RVA/s800/pyamf-logo-362x80.jpg" /></a><br /><br />有用 <a href="http://http://pyamf.org/">PyAMF</a> 來和 flash 坐資料傳輸，在寫  Django 的 test case，還要另外把 dev server 跑起來，才可以跑測試，這是一個，Unittest 的 test client 直接可以像 Django django.test.client 裡的 Client 直接對應 url 的方式來跑<br /><br /><a href="http://hg.io/madssj/pyamf-django-testclient/src/tip/client.py">http://hg.io/madssj/pyamf-django-testclient/src/tip/client.py</a><br /><br /><br />如果，不用 unitetest 用簡潔的 nose 寫 test case 可以把他所有的 self.logger 的程式標成註解<br /><br /><code><br />from django.test.client import Client<br /><br />client = PyAMFClient(Client(), '/your_gateway_url/')<br />service = client.getService('your_service')<br /><br /></code><br />也可以直接跑 test case
