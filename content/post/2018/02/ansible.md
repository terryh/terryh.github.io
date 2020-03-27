+++
title = "Ansible"
date = 2018-02-10T22:51:00Z
updated = 2018-02-10T23:09:29Z
tags = ["Debian", "GNU/Linux", "Python"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

更新，這一篇，是一段時間前寫的，居然發現，有沒發的文<br />現在小弟，也跳過 ansible 了，改用容器化的方案 (真不專情)<br /><br /><a href="http://www.ansible.com/home">Ansible</a> 簡單的系統部屬工具，是用 Python 撰寫的佈署工具，有點像是 puppet , chef , salt 的工具<br /><br />主要原理，就是透過 ssh 的方式，算是非常單純簡單的方式，比起 puppet 或是 chef 來說<br /><br /><br />這一篇，我想筆記的是對 Google Cloud Engine 上面 VM 的佈署，安裝就用 python 的 pip 就可以了，因為對 GCE 的支援，是透過 libcloud 的套件做的<br />所以，你除了要安裝 ansible 外，也是裝 libcloud ，用 pip 的話，安裝像是這樣，看你的系統需不要加 sudo ，因為，我是在 Mac 上面，整個 /usr/local <br />都是我在用，所以我不用加，實際依自己的系統情形<br /><br /><br />
<pre>
<code class="bash">
pip install ansible apache-libcloud
</code>
</pre>

設定 gce.ini<br />gce.ini <a href="https://github.com/ansible/ansible/blob/devel/plugins/inventory/gce.ini">https://github.com/ansible/ansible/blob/devel/plugins/inventory/gce.ini</a><br />gce.py <a href="https://github.com/ansible/ansible/blob/devel/plugins/inventory/gce.py">https://github.com/ansible/ansible/blob/devel/plugins/inventory/gce.py</a>

<pre><code class="bash">
export GCE_INI_PATH=/pathto/gce.ini
export ANSIBLE_HOSTS=/pathto/gce.py
</code>
</pre>

請先手動建立，一個 VM ，我沒仔細深究，為什麼一定要有一台 VM<br /><br />ansible all -m ping<br /><br />這時候，應該要可以看到，你已經有的 GCE VM<br /><br />ansible-playbook -v gce.yml<br /><br /><br /><br />參考文章<br /><br /><a href="https://doitintl.zendesk.com/hc/en-us/articles/202342715-How-to-install-Ansible">https://doitintl.zendesk.com/hc/en-us/articles/202342715-How-to-install-Ansible</a><br /><br /><a href="http://www.codedata.com.tw/social-coding/ansible-github/">http://www.codedata.com.tw/social-coding/ansible-github/</a>
