+++
title = "uWSGI"
date = 2011-04-11T17:53:00Z
updated = 2011-04-11T18:55:02Z
tags = ["Nginx", "Python", "uWSGI"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="http://projects.unbit.it/images/logo_uWSGI.png" alt="uWSGI" /><br /><br /><a href="http://projects.unbit.it/uwsgi/wiki">http://projects.unbit.it/uwsgi/wiki</a> 是完全用 C 來實做的 wsgi server ，wsgi 就是目前 Python web 配置方式中最為通用的方式 <br /><br />現在 <a href="http://nginx.org/">nignx</a> 預設已經有支援了 <br /><br />我覺得最棒的是，哈哈看看安裝方式 <a href="http://projects.unbit.it/uwsgi/wiki/Install">http://projects.unbit.it/uwsgi/wiki/Install</a>， 喔耶<br /><br />pip install uwsgi<br /><br /># OR<br /><br />pip install http://projects.unbit.it/downloads/uwsgi-lts.tar.gz<br /><br /><br />你說，有沒有想按個讚壓，以後就不能說， uWSGI deploy 麻煩，綠角馬 ( <a href="http://gunicorn.org/">gunicorn</a>) 比較方便了<br /><br />試試看才知道真實力， session 搬到，記憶體，或是 cache 後， <a href="http://gunicorn.org/">C10K</a> 應該可以輕鬆一些<br /><br />PS 給新手，老手可跳過: 鄉親壓，當然還是要設定檔地，請參考 <a href="http://projects.unbit.it/uwsgi/wiki/Example">http://projects.unbit.it/uwsgi/wiki/Exampl</a> ，記得可以搭配 <a href="http://cr.yp.to/daemontools.html">daemontools</a> ，或是 <a href="http://upstart.ubuntu.com/">Upstart</a> 一起服用喔 ，千萬不要天真又善良的由 source 安裝喔，各大 Linux distribution 都有販售
