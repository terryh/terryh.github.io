+++
title = "Python 包 EXE"
date = 2012-10-20T02:44:00Z
updated = 2012-10-20T02:45:46Z
tags = ["Windows", "Python"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

關於目前 Python windows 程式打包的方式選擇也算蠻多的<br /><br />有用過一些，說一說心得吧<br /><br /><a href="http://www.py2exe.org/">py2exe</a> <br /><br />安裝後，直結整合到 setup.py 裡<br />歷史悠久，但是看起來很久沒有後續的維護，一開始我都是用這一個打包，算是很穩定<br /><br /><a href="http://www.pyinstaller.org/">pyinstaller</a><br /><br />後起之秀，single file 的打包方式，算是功能蠻強的，執行時，是解壓到暫存資料夾執行，但是hook 一大堆，解決非常多的套件問題，也算是一種 dirty  hack <a href="https://github.com/pyinstaller/pyinstaller">https://github.com/pyinstaller/pyinstaller</a>，算有在維護，小程式可以用他來打包執行也算簡單， 2.0 以後，打包更容易<br />不需要安裝，直接解壓縮後執行，有用到 multiprocessing 的模組的人，他的 importHook 蠻容易造成動態載入模組的問題，像是程式裡用 __import__ 來載入模組的方式，都蠻容易有問題的，再來就是 hook 程式很多，如果用的第三方模組沒有支援，就非常的難包，需要自己客製寫 spec 檔<br /><br />python pyinstaller.py -F -d -i your_app/app.ico your_app/app.py<br /><br />-F 包單一執行檔<br />-D 包成一個資料夾<br />-d debug 打開<br />-i 程式 icon<br /><br />會產生 your_app/app.spec 檔案，後續可以再手動調整 app.spec，再執行，其實執行 spec 檔時，沒有加 options 沒關係<br /><br />python pyinstaller.py -F -d -i your_app/app.ico your_app/app.spec<br /><br /><a href="http://cx-freeze.sourceforge.net/">cx_Freeze</a> <a href="https://bitbucket.org/anthony_tuininga/cx_freeze/src">https://bitbucket.org/anthony_tuininga/cx_freeze/src</a><br /><br />實作的方式，比較像是 py2exe ，是寫 setup.py 整合，簡單的也可以直接下 cxfreeze 打包，不能包 single file exe，可以另外用工具包起來，文件比較缺乏，唯一有支援 Python3 <br />安裝完後，可以直接參考範例寫 setup.py ，要注意的是安裝完後放到 Scripts 裡的程式有路徑的問題要先修一下<br />我用 Python27 的例子 Scripts\cxfreeze 裡的 Python 路徑是 C:\Python\32-bit\2.7\python.exe ，請自己修改成您的<br />python.exe 的路徑<br /><br />python setup.py build 就可以了<br /><br /><br />目前小的程式，會用 pyinstaller<br />大一點的程式，會用 cx_Freeze<br /><br /><br />
