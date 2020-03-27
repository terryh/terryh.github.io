+++
title = "Django with PayPal"
date = 2010-08-12T02:32:00Z
updated = 2011-12-11T07:47:01Z
tags = ["Web", "Django", "PayPal"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<a href="https://www.paypal.com/tw"><img src="http://lh4.ggpht.com/_Bsjm2Qp0Duc/TIr5zJvlLbI/AAAAAAAAA-o/jE3v8j006ho/s800/paypal-logo-black.jpg" /></a><br /><br />要接付對大家最方便的應該還是 PayPal，畢竟，他運行的時間比較久<br /><br />基本的方式， Web Form 或是 API 的方式，可以直接用 djangosnippets 的程式範例<br /><br /><a href="http://djangosnippets.org/tags/paypal/">http://djangosnippets.org/tags/paypal/</a><br /><br />在加上 <a href="http://uswaretech.com/blog/2008/11/using-paypal-with-django/">http://uswaretech.com/blog/2008/11/using-paypal-with-django/</a><br /><br />這樣，很快就可以用啦<br /><br />Web Form (PayNow)，基本上，基本的元素<br /><br />這是由文件的範例<br /><script src="http://gist.github.com/520700.js"> </script><br /><br /><br />但是我會再加上(加到 web form 裡)<br /><code><br />input type="hidden" name="rm" value="2"<br />input type="hidden" name="return" value="http://somewhere after payment"<br />input type="hidden" name="cancel_return" value="http://user cancel"><br />input type="hidden" name="notify_url" value="http://url to handle Paypal callback"<br /></code><br /><br /><br />API <br /><br />就直接照上面國外部落格作者寫得的就可以了
