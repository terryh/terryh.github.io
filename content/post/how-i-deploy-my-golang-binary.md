+++
title = "How I deploy my golang binary"
date = 2015-07-09T20:18:00Z
updated = 2015-07-09T20:57:57Z
tags = ["Golang", "GNU/Linux", "Docker"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在網路上，有很多 Docker 的佈署的文章，或是用來測試的方式<br /><br />用 golang 撰寫的服務，編譯成執行檔後，你可以有很多的選擇，例如：upstart ， supervisord ， 或是 daemontools<br /><br />這一次，我想用 Docker ，想要他的彈性<br /><br />但是，不管用 Ubuntu ， Debian 或是官方的 <a href="https://registry.hub.docker.com/_/golang/">Golang</a> 的 image<br /><br />總覺得 image 太大，不合用，直接由 scratch 做 image 又覺得，萬一有一些系統的相依套件，需要的時候，不方便<br /><br />所以這是我目前的萬用 image 的 Dockerfile<br /><br /><pre><code><br />FROM alpine:3.2<br />RUN apk --update add curl<br />WORKDIR /usr/src/app<br />ENTRYPOINT  ["/usr/src/app/goapp"]<br /></code></pre><br />實際的編譯執行檔，分資料夾放，名字都叫做 goapp，執行 container 的時候，用 -v 掛載進 container 的 /usr/src/app <br />golang 的程式記得可以用環境變數，更改一些執行的變數，像是，資料庫連結，等等，只要執行 container 時，用 -e 帶給 container <br /><br />以後上新版的執行檔，就只要下 docker restart your_running_container 而已<br /><br /><br />image 裡安裝的 curl ，只是要順便把 ssl certificates 安裝，這樣就有 root certificates <br /><br />這樣的 images 大小大約 8.7 MB ，夠小，也很快<br />
