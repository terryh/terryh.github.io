+++
title = "Unifi Controller"
date = 2021-11-24T20:47:41+08:00
draft = false
tags = ["unifi", "raspberry"]
+++

最近有點想換 UniFi 的 AP 分享器，但是只有分享器，switch 並沒有想要換

所以也就不太需要單純為了幾台 AP 分享器，而買一台比分享器單價還高
的 unifi controller 了，這裡簡單用宅男家裡一定有多一片的 raspberry pi ，
簡單安裝，unifi 的控制器，跑在上面管理，即可。

如果您家已經有 NAS 的話，也可以用 docker 的方式，部屬執行在 NAS 上面

<!--more-->

步驟如下

1. 準備 raspberry pi 的 SD 卡，我是 lite 的版本

2. 您可以先在 /boot 上，touch 一個 ssh 檔案，預設啟動 sshd server

3. 您可以先在 /boot 上面，預先設定您的網路分享器帳號，密碼，這樣就可以自動連上無線網路，
可以去 IP 分享器上面查看動態分配的 IP 位置，就可以直接用 ssh 連線


```console
# 檔案 /boot/wpa_supplicant.conf
country=TW
update_config=1
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev

network={
    scan_ssid=1
    key_mgmt=WPA-PSK
    ssid="你的SSID"
    psk="密碼"
}
```

4. 安裝 unifi controller 

請直接下載安裝 script 執行

https://glennr.nl/s/unifi-network-controller

https://community.ui.com/questions/ccbc7530-dd61-40a7-82ec-22b17f027776

5. 安裝完後，用瀏覽器，連到您的 raspberry pi 機器的 https://您raspberry PI 的ip 位置:8443 信任憑證，這樣就可以了
