+++
title = "Google Photo Embed"
date = 2018-03-26T09:49:33+08:00
tags = ["開發工具", "相簿"]
+++
![Google Photo](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4f/Google_Photos_icon.svg/480px-Google_Photos_icon.svg.png)

現在用 [Hugo](https://gohugo.io/) 以靜態網頁的方式寫東西

常常需要把圖片嵌入到網頁當中

Picasa 被 Google 殺了後，自己大多是用，Google Photo 

<!--more-->

用 android 手機的人就圖他方便

看起來，也不太會倒，短期的未來，Google 應該還不至於會放倒這個服務，

這種吃網路資源的東西，其實要很多錢來燒，服務才能做到位的

用 android 手機就一直加減用， 目前 Google Photo 沒提供給你可以把照片，嵌入網頁的功能，

不知道是故意的，還是想要強推，相片分享的方式，帶一下他們自家的 Google Plus

參考了網路上面的文件後，程式沒幾行，自己圖片連結自己抓的概念

參考文件 [How to Embed Images from Google Photos into your Website](https://www.labnol.org/internet/embed-google-photos-in-website/29194/)

安裝方式，在已經有 golang 的環境直接打
<pre>
<code class="bash">
go get github.com/terryh/google_photo_img/cmd/gphoto2img
</code>
</pre>

就有了 gphoto2img 可以用了，直接 gphoto2img your_google_photo_sharelink

就會吐出，Google Photo 可以嵌入的 html， url link with image tag

Happy Writing Happy Coding
