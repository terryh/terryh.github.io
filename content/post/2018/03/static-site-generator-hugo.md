+++
title = "Static Site Generator Hugo"
date = 2018-03-29T10:47:15+08:00
tags = ["Blog", "Web"]
+++

![Hugo](https://gohugo.io/img/hugo-logo.png)

<a href="https://gohugo.io/">https://gohugo.io/</a>

靜態網站生成器

<!--more-->

TLDR

Hugo 安裝 

on Mac
<pre>
<code class="bash">
brew install hugo
</code>
</pre>

用 Linux 的朋友，你一定可以，因為它是 Golang 寫的

建立新網站 yoursite

<pre>
<code class="bash">
hugo new site yoursite
</code>
</pre>

Hugo 目錄結構

<pre>
<code class="bash">
.
├── archetypes
├── config.toml
├── content
├── data
├── layouts
├── public
├── static
└── themes
</code>
</pre>

* archetypes 定義
* config.toml 設定檔
* content 書寫內容的資料夾
* data
* layouts 自定義網站模板
* public 預設產生靜態檔的位置
* themes 安裝現在的模板， <a href="https://themes.gohugo.io/">https://themes.gohugo.io/</a>

建立一遍文章 (會產生在 content/post/2018/03/first-post.md )
格式會依照你的 archetypes/default.md 檔案

<pre>
<code class="bash">
hugo new post/2018/03/first-post.md
</code>
</pre>

起動本機靜態伺服器，可以邊寫邊改，預設是 http://localhost:1313
<pre>
<code class="bash">
hugo server -D
</code>
</pre>

重新產生靜態檔案，就打 hugo 就好
<pre>
<code class="bash">
hugo
</code>
</pre>

自定模板，可以先找喜歡的風格當基底，然後， 複製想要客製化的部份到 layouts 資料夾下面，開始自己客制 這一部分，可以參考文件，也有 hugo 本身自帶的簡單模板， 預設的大多 css 定義，都是依照 bootstrap 的語法

Hugo 好東西，用過的就懂 (聳肩中...)


最近把部落格由， Blogger 搬家到由靜態網頁產生的方式，希望從此可以過著快樂的生活，
簡化書寫的習慣，回到最原始的方式，簡單寫，分享易，不用弄平台，由於，最後是靜態網頁，
部署維護也變的很簡單

先帶一下，目前大家寫文章的方式好了

這裏說的都主要以西方社會，或是可以自由上網沒有圍牆或是限制的國家

平台來說 Medium ， Wordpress ， Blogger
國內實在找不太到上的了台面的 
靜態產生的方式可以參考這一遍

<a href="https://www.netlify.com/blog/2017/05/25/top-ten-static-site-generators-of-2017/">https://www.netlify.com/blog/2017/05/25/top-ten-static-site-generators-of-2017/</a>

或是更多的人都是指直接寫 Twitter ，或是 FB，文彩或是屁話，隨著資訊的洪流一樣消失在大海

身為一個工程師，說什麼也要把內容放自己的網域 (阿宅的堅持，不要攔我)， 
持續寫一寫自己想寫的東西， 無比的療癒，好處數不完，我簡略一二，各位聽聽就好，
可以針砭時事，療癒，年紀越大，可作筆記， 不用擔心，那個平台又收了，
你要把文章搬家，展現出成熟開發宅忍耐，專一， 堅持的特質，我現在就可以跟你屁，
你看，我部落格寫了十幾二十年， 雖然默默無聞，這就就叫，堅持


