+++
title = "multiprocessing in wxPython"
date = 2012-04-22T19:45:00Z
updated = 2012-04-23T19:41:33Z
tags = ["wxPython", "Python"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

根據 wiki 上面的文件說 <a href="http://wiki.wxpython.org/MultiProcessing">http://wiki.wxpython.org/MultiProcessing</a><br /><br />不可以在 wx.App 的程式迴圈中，去產生新的 Process<br /><br />真的試了一下，還真不行，在不用 threading, subprocess, 或是 wx.Process 的寫法下，只要把產生新 Process 的動作移出 <br /><br />wx.App 的範圍裡就沒有問題了<br /><br />另外如果程式是用 <a href="http://www.pyinstaller.org/">pyinstaller</a> 包裝成一個檔案，也要注意這 Process 需要重包來解決問題<br /><br /><a href="http://www.pyinstaller.org/wiki/Recipe/Multiprocessing">http://www.pyinstaller.org/wiki/Recipe/Multiprocessing</a><br /><br /><br />筆記一下，以免以後忘了
