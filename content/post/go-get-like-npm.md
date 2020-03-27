+++
title = "go get like npm"
date = 2013-02-07T08:01:00Z
updated = 2013-02-12T22:43:31Z
tags = ["Golang", "Node.js"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在 <a href="http://golang.org/">Go</a> 下面想要安裝套件，可以像是用 <a href="http://nodejs.org/">node.js</a> 的 <a href="https://npmjs.org/">npm</a> 安裝不加 global 的參數，做本地端的安裝嗎？<br /><br />建立 shell script gopm 放在您的 $PATH 中的路徑<br /><br /><pre>#!/bin/bash<br /># Uasge:<br />#       gopm get some package from github<br />#       gopm run yourmain.go<br />OLDGOPATH="$GOPATH"<br />export GOPATH=$PWD<br />go $*<br />export GOPATH="$OLDGOPATH"<br /></pre><br />或是都是在本地端開發，不太在意覆蓋原本的 GOPATH，直接像是加在 .bashrc  的環境裡<br /><br /><pre>alias gopm='export GOPATH=`pwd` &amp;&amp; go'<br /></pre><br />只要用 GOPATH 這一個環境變數，就可以達到了，所以這樣設定以後，執行的時候，就會用目前的資料夾當作，GOPATH ，套件也就都會安裝在執行時的目錄<br /><br />執行程式測試的時候也一樣，假設叫 gopm ，就用 gopm run yourmain.go 就可以了<br /><br />安裝需要的套件和 go get 一樣，例如在所在專案路徑安裝所有相依套件，原本打 <br /><br />go get<br /><br />會裝到 GOROOT 路徑下<br /><br />換成打 <br /><br />gopm get<br /><br />因為加了目前專案路徑($PWD)為 GOPATH ，所以安裝到目前的資料夾下<br /><br /><br />PS: gopm 只是我自己隨便取的，文件及 source code 裡是有提到，不可以和 GOROOT 同一個資料夾，不過這不是廢話嗎 XD<br />UPDATE: 在 mail list 上面當小白後，GOPATH 不要去覆蓋他，會影響到整的 GO 環境 build 變數，以我目前的了解會用暫時覆蓋的方式，有比較好的方式再來更新
