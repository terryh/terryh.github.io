+++
title = "Get your Node"
date = 2012-01-05T20:15:00Z
updated = 2012-01-05T23:41:43Z
tags = ["Node.js", "JavaScript"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="http://nodejs.org/logos/nodejs-green.png" alt="node.js "/><br /><br />MEMO 一下 Debian testing 上面的 Node 安裝<br /><br />實在進步太快了，裝 pre compiled 的套件沒有感覺<br /><br /><pre>sudo apt-get install build-essential python-software-properties libssl-dev libreadline-dev git-core curl libcurl4-openssl-dev<br /></pre><br />記一下 libcurl4-openssl-dev # 只是目前 debian testing 上面依存的套件<br /><br /><pre>git clone https://github.com/joyent/node.git<br />cd node<br />git checkout v0.6.6 # 目前最新的 release tag<br />./configure<br />make<br />sudo make install<br /></pre><br /><br /><br />發展快速，社群活躍，最重要就像的第四台老師有說得 Location, Location, Location <br /><br />Node.js 是 Open, Open, Open (community, community, community, 內建的 npm 套件管理, 這一點夠方便吧)<br /><br />想要變高，變帥，變聰明前，不要忘了，上場前，把 node.js 的傢伙戴上<br /><br /><a href="http://www.webresourcesdepot.com/the-awesome-node-js-and-its-gang/">http://www.webresourcesdepot.com/the-awesome-node-js-and-its-gang/</a><br /><br /><a href="https://github.com/joyent/node/wiki/modules">https://github.com/joyent/node/wiki/modules</a><br /><br />參考<br /><a href="http://fred-zone.blogspot.com/2011/12/debian-nodejs-express.html">http://fred-zone.blogspot.com/2011/12/debian-nodejs-express.html</a><br /><br /><a href="http://www.freshblurbs.com/install-node-js-and-express-js-nginx-debian-lenny">http://www.freshblurbs.com/install-node-js-and-express-js-nginx-debian-lenny</a><br /><br /><br />八卦一下，我的 VPS RAM 太小，本來是要說 Get your JVM，不過看起來，這一隻怪獸，還是要找多一點 RAM 的主機，才願意開始幹活<br /><br /><pre>terry@atomvm:~/node$ java -version<br />Error occurred during initialization of VM<br />Could not reserve enough space for object heap<br />Could not create the Java virtual machine.<br />terry@atomvm:~/node$ node -v<br />v0.6.6<br /></pre>
