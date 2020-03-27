+++
title = "Chrome cache in RAM"
date = 2012-11-08T17:34:00Z
updated = 2012-11-08T18:02:09Z
tags = ["Chrome", "Debian", "GNU/Linux"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

<img src="https://lh5.googleusercontent.com/-Q5mUz0puzZM/TIroahUEp4I/AAAAAAAAA94/P8KebvVBsEQ/s144/200px-Chrome_Logo.svg.png" /><br /><br /><br />在 Linux 上面已經有當多簡單的教學，不過大多是教修改設定檔的方式，以下是更簡單的方式<br /><br />以 Debian GNOME3 的環境為例<br /><br />應用程式-->主選單-->網際網路  ，在 Debian "主選單" 的程式名字是 alacarte<br /><br />選 chrome 後，右邊有屬性的條件可以修改，把指令欄位修改成下面，就可以啦，只要 --disk-cache-dir 的 option 即可<br /><br /><br />/opt/google/chrome/google-chrome  --disk-cache-dir="/tmp/chrome/" %U
