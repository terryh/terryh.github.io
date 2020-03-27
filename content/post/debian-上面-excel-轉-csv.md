+++
title = "debian 上面 excel 轉 csv"
date = 2013-04-18T20:56:00Z
updated = 2013-04-18T20:56:56Z
tags = ["Debian"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

應該所有可以裝 libreoffice 的 unix like 的系統應該都可以<br /><br />我是在 debian 上面，可以裝 unoconv 套件<br /><br />apt-get install unoconv<br /><br />之後就可以用<br /><br />unoconv -f csv filename.xlsx<br /><br />參考資料<br /><br /><a href="http://unix.stackexchange.com/questions/23726/convert-a-xlsx-ms-excel-file-to-csv-on-command-line-with-semicolon-separated">http://unix.stackexchange.com/questions/23726/convert-a-xlsx-ms-excel-file-to-csv-on-command-line-with-semicolon-separated</a>
