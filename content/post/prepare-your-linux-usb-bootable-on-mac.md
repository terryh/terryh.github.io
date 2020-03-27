+++
title = "Prepare your Linux USB bootable on Mac"
date = 2015-05-08T07:53:00Z
updated = 2015-05-08T08:08:39Z
tags = ["Debian", "GNU/Linux", "Mac"]
blogimport = true 
[author]
	name = "TerryH"
	uri = "https://www.blogger.com/profile/00198432946574471177"
+++

在 Mac 上面要準備你的 GNU/Linux USB 安裝拇指碟<br /><br />沒有像上 Linux 上面這麼的方便，畢竟這就是華麗的代價<br /><br /><br /><br />基本步驟，這裡指的是 Debian 的安裝 ISO 檔案為例<br /><br />1) 下載 ISO <a href="http://cdimage.debian.org/debian-cd/8.0.0/amd64/iso-cd/debian-8.0.0-amd64-netinst.iso">http://cdimage.debian.org/debian-cd/8.0.0/amd64/iso-cd/debian-8.0.0-amd64-netinst.iso</a><br /><br /><br />2) 轉檔 hdiutil convert -format UDTO -o debian.img debian-8.0.0-amd64-netinst.iso<br /><br />3) 找到你 USB SD 卡的磁碟名稱 diskutil list<br /><br />4) 我的例子是 /dev/disk3<br /><br />5) diskutil umountDisk /dev/disk3 卸載<br /><br />5) 切割 USB 碟，格式化， diskutil partitionDisk /dev/disk3 1 "Free Space" "unused" "100%"<br /><br />6) sudo dd if=debian.img.cdr of=/dev/disk3 bs=1m<br /><br />恭喜，這樣可以做完收工了，可以有 Linux USB 安裝拇指碟 <br /><br /><br />參考資料<br /><a href="http://blog.tinned-software.net/create-bootable-usb-stick-from-iso-in-mac-os-x/">http://blog.tinned-software.net/create-bootable-usb-stick-from-iso-in-mac-os-x/</a><br /><br /><a href="http://unix.stackexchange.com/questions/114984/how-to-create-a-bootable-linux-installation-usb-from-an-iso-in-os-x">http://unix.stackexchange.com/questions/114984/how-to-create-a-bootable-linux-installation-usb-from-an-iso-in-os-x</a>
