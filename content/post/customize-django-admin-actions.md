+++
title = "Customize Django Admin actions"
date = 2011-08-31T23:12:00Z
updated = 2011-08-31T23:12:13Z
tags = ["Python", "Django"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

雖然，大大說這是一個 Design decision<br /><br />也說行為不會改變 <br /><br /><a href ="https://code.djangoproject.com/ticket/10768">https://code.djangoproject.com/ticket/10768</a><br /><br /><a href="http://stackoverflow.com/questions/4500924/django-admin-action-without-selecting-objects">http://stackoverflow.com/questions/4500924/django-admin-action-without-selecting-objects</a><br /><br />有些時候，想簡單的整合在一起，還是要找一些洞來繞<br /><a href="https://github.com/django/django/blob/master/django/contrib/admin/options.py#L856">https://github.com/django/django/blob/master/django/contrib/admin/options.py#L856</a><br /><br />純筆記
