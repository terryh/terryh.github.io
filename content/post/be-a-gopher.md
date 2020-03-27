+++
title = "Be a gopher"
date = 2012-12-14T22:19:00Z
updated = 2012-12-15T23:46:02Z
tags = ["Golang"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="http://golang.org/doc/gopher/frontpage.png" alt="golang" /><br /><br />試試 <a href="http://golang.org/">golang</a> 的過程，做一下筆記<br /><br />基本上，是很棒的開發體驗<br /><br />優點<br /><br />1. 語法簡潔，但是嚴謹，限制 import 的位置，function name 的第一個字大小寫代表 public 或是 private ，程式中沒有用到的 import module 或是 variable 會有編譯錯誤，編譯速度飛快，和 Java 及 C++ 比較，你一定會感動到流眼淚，當然不拿什麼 IDE 快捷鍵，或是安裝插件的功能，單純語言本生的語法探討，C 的 pointer，Python 的 slice ，anonymous function <br /><br />2. 用 type struct , type interface , receiver function 的方式，達到類似物件導向的繼承多型，介面功能(我也不是什麼物件導向專家，無法做更深層的探討)<br /><br />3. 語言本質上的簡化，讓學習的曲線平緩，像是在寫手稿語言一樣，人員訓練比較容易 (像是找一個，會C++ 的可能一年，說的上熟 C++ 的可能要N年 XD )<br /><br />4. 內建 automatic garbage collection ，基本上，不需要去個別管理記憶體，不過這個特性記得不要濫用 XD<br /><br />5. Concurrency 有 gorountine 及 channel 的實作方式，也有像傳統 threading 方式的實作方法，簡化很多<br /><br />6. gofmt 定義一致簡易的 coding style，對程式碼日後的可讀性有幫助<br /><br />7. 內建 testing 的模組及結構<br /><br />缺點<br /><br />1. 工作機會少 (如果你是抱著開心的心態，這一點沒差)<br /><br />2. 可用成熟第三方模組比較少，像是 Java ( Maven Central)，Ruby(gem)，Python(pypi)， javascript (npm) (這一點很難說，目前golang 就可以直接在 import 區塊 import  hg, git, svn 還有 bzr 的 source tree ，到底集中式，還是分散式好，很難說，但是有一個套件管理中心很重要，像是 javascript 的 npm 粉贊) ，目前 golang 可以看到的套件 <a href="http://godoc.org/">http://godoc.org/</a> 大約 6000 多個套件左右，再扣一些測試，或是非常 beta 的套件，目前第三方模組比較缺乏<br /><br /><br />說完了，有興趣的朋友可以繼續看<br /><br />如何入門，真的很簡單，一般看一份蘋果日報的時間，基本的語法就可以看完了<br />有 C ，Python ，Java，Ruby 基礎的朋友可能更快，最下面有書本的連結<br /><br />建置環境<br /><br />1. 直接由官方網站下載安裝，FreeBSD ，Mac，Linux，Windows 都有，我主要的說明是在 Debian Linux  下面進行，下載 <a href="https://code.google.com/p/go/downloads/list">https://code.google.com/p/go/downloads/list</a> ，安裝說明 <a href="http://golang.org/doc/install#introduction">http://golang.org/doc/install#introduction</a><br /><br />2. 設定 env ，記得把 GOBIN 的路徑加到 $PATH 裏面，windows 的朋友請進行設定環境變數<br />
<pre>
<code class="bash">
GOBIN=/usr/local/go/bin
GOROOT=/usr/local/go
</code>
</pre>
3. 將 /usr/local/go/misc/bash/go 複製到 /etc/bash_completion.d/ 下面，用 zsh 的朋友也可以在 misc 資料夾下面看到對應的檔案，這樣以後 go 指令在 terminal 下，就可以 autocomplete 了<br /><br />4. 編輯環境，在安裝完 go 以後，可以用指令安裝 go get -u github.com/nsf/gocode ， 這裡的安裝路徑，裝完後，source 會放在 $GOROOT/src/pkg/github.com/nfs/gocode 下面，gocode 會放在 $GOROOT/bin 下，這樣的安裝路徑，再開發自己的套件時，也可以直接寫在 source code 的 import block 中，完整的 gocode 的安裝說明，請參考<br /><a href="https://github.com/nsf/gocode">https://github.com/nsf/gocode</a>， 另外 vim 或是 emacs 的 syntax highlight 也可以都可以在 /usr/local/go/misc 下面找到，要是 vim 和我一樣是用 vundle 的方式管理，可以在 .vimrc 裡加上 Bundle 'jnwhiteh/vim-golang.git' 後 BundleInstall ，就不用將 misc 底下的 vim設定，複製到 .vim 資料夾下面，gocode ，最後要到 gocode 資料夾下面的 vim 子目錄執行, update.bash 他的內容<br />
<pre>
<code class="bash">
#!/usr/bin/env bash
mkdir -p ~/.vim/{autoload,ftplugin}
cp autoload/gocomplete.vim ~/.vim/autoload
cp ftplugin/go.vim ~/.vim/ftplugin
</code>
</pre>
這樣裝完 vim 下面就可以有 omnicomplete 了，如下圖<br /><img src ="http://nosmileface.ru/images/gocode-screenshot.png" width="600" /><br /><br />用 Eclipse 的朋友 <a href="http://code.google.com/p/goclipse/">http://code.google.com/p/goclipse/</a><br /><br />開始玩樂<br /><br />1. 看 source module 文件 ，打 go doc ，或是自己看 go help 自己看文件，可以查 go doc fmt 或是 go doc crypto/md5<br />
<pre>
<code class="bash">
go doc fmt
go doc crypto
go doc crypto/md5
</code>
</pre>

或是，直接執行文件伺服器類似 Python 下 pydoc 一樣，只是換成 godoc ，請 godoc -h 直接看文件，範例是 doc server 跑在 6000 port ，打開瀏覽器到 http://localhost:6000 ，就可以直接看模組文件了

<pre>
<code class="bash">
godoc -http=":6000"
</code>
</pre>

2. 很多內建模組，也是直接以 golang 撰寫，直接看 source code ，簡單易懂，可以看的整的語言設計簡化帶來的好處<br /><br />3. hello world，main.go 打完後，執行 go run main.go

<pre>
<code class="go">
package main
import "fmt"
func main() {
    fmt.Println("Hello World")
}
</code>
</pre>

開始前，先花一點時間看看基本語法<br /><br />1. <a href="http://www.golang-book.com/">http://www.golang-book.com/</a><br /><br />2. <a href="http://www.miek.nl/projects/">http://www.miek.nl/projects/</a><br /><br /><br />Have fun<br /><br />PS: 我指的簡單是指語法上的簡單易學，純就語言上，不是探討要實作的內容
