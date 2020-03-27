+++
title = "SQL like in pymongo"
date = 2011-08-03T00:19:00Z
updated = 2011-08-11T07:11:51Z
tags = ["Python", "MongoDB"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在 MongoDB &nbsp;的網站上面，看到用 javascript query 的語法 LIKE 對應的語法，在 pymongo 不知道怎麼對應<br /><br />筆記一下<br /><br />這是 文件的範例<br /><br />SQL<br /><code><br />SELECT * FROM users WHERE name LIKE "%Joe%"<br /></code><br /><br />MongoDB 文件<br /><code><br />db.users.find({name:/Joe/})<br /></code><br /><br />pymongo 的操作<br /><code><br />db.users.find({'name':re.compile('Joe')})<br /></code><br /><br /><br />依此類推，當然記得要 import re <br /><br /><br /><a href="http://www.mongodb.org/display/DOCS/Advanced+Queries">http://www.mongodb.org/display/DOCS/Advanced+Queries</a><br /><br /><a href="http://www.mongodb.org/display/DOCS/SQL+to+Mongo+Mapping+Chart">http://www.mongodb.org/display/DOCS/SQL+to+Mongo+Mapping+Chart</a>
