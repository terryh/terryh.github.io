+++
title = "WSDL use suds"
date = 2012-09-11T19:08:00Z
updated = 2012-09-11T19:08:24Z
tags = ["Python", "WSDL"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在 Python 的函式庫裡， suds 算是通用的選擇，一直用起來也算蠻穩定的<br /><br />不過在一些比較特別的網路環境裡，或是需要參照其他 XMLSchema 的時候<br /><br />我比較沒有經驗，所以紀錄一下，這一個環境機器連結外部 80 port 的服務要透過 proxy<br /><br /><pre><br />proxy_config = {'http': 'http://someproxy.host:3128'}<br /><br />from suds.xsd.doctor import Import, ImportDoctor<br />from suds.client import Client<br /><br />wsdl_url = 'http://somewebservice.com/service.asmx?WSDL'<br /><br />imp = Import('http://www.w3.org/2001/XMLSchema', location='http://www.w3.org/2001/XMLSchema.xsd')<br />imp.filter.add('http://tempuri.org/')<br /><br />client = Client(wsdl_url, doctor=ImportDoctor(imp), proxy=proxy_config)<br /><br />print client # read avaliable api ;-)<br /><br /></pre><br /><br />參考資料<br /><br /><a href="http://stackoverflow.com/questions/5769128/soap-client-using-suds">http://stackoverflow.com/questions/5769128/soap-client-using-suds</a>
