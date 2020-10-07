+++
title = "Amdgpu Unreal Engine"
date = 2020-10-04T16:39:09+08:00
tags = ["GNU/Linux", "AMDGpu", "Debian", "Ubuntu", "UnrealEngine"]
+++

updated 2020.10.07 success 2 (目前推薦的方式)

因為最近重回 linux 懷抱，這一次，沒有選 Debian 而是使用
比較偏大眾口味的 Ubuntu 原因沒有太特別，就單純第三方支援比較多，

我使用的處理器也是，AMD 非常新款的處理器 AMD Ryzen 5 Pro 4650G

有良好的處理器效能，及堪用的 GPU 可以供運用，原本在 UnrealEngine 有點卡關

所以分享一下，也許可以幫到有需要的人，

我先把我遇到的問題，寫一下，這樣 Google 才會找到

OS Ubuntu 20.04
UnrealEngine 4.24

目標，可以跑 

CARLA simulator https://carla.org/

AirSim https://github.com/Microsoft/AirSim

<img src="https://lh3.googleusercontent.com/8AKRngJD2GG-YL7M3NNOh6-k6csDIZGWzBgzdwohj_k8JmzySgEkjlcP2H_41n09DHoP3JVEybyNt47X6bnn5gs-VYb54hpFbhfZNWlsEeul1XViKKK-T_AoXYXtEtpDUlxQPiQodtw=w600-h315-p-k" />

<!--more-->

# scenario 1 

Ubuntu 20.04 安裝，使用系統預設的 kernel 版本，預設的 gpu driver ，
glxinfo 顯示沒有問題，vulkeninfo 查看資訊時，無法支援，跑 UnrealEngine 時，出現錯誤


# scenario 2

Ubuntu 20.04 安裝，使用系統預設的 kernel 版本，amdgpu pro deiver 20.30，
https://www.amd.com/zh-hant/support/kb/release-notes/rn-amdgpu-unified-linux-20-30

安裝方式 ./amdgpu-pro-install -y

進入 Gnome 桌面，開視窗程式，邊框會有雪花現象，沒有顯示特別錯誤，圖形桌面有問題，就沒有繼續試 UnrealEngine 了


# scenario 3

Ubuntu 20.04 安裝，使用系統預設的 kernel 版本，amdgpu pro deiver 20.20，
https://www.amd.com/zh-hant/support/kb/release-notes/rn-amdgpu-unified-linux-20-20

安裝方式 ./amdgpu-pro-install -y

進入 gonme 桌面沒有問題 執行 glxinfo 及 vulkaninfo 都正常，但開 UnrealEngine 時，會出現 amdgpu_dri.so 的錯誤，上面寫
Function not found 的錯誤

這時候，可以用 amdgpu-pro-install --uninstall 把驅動及相關的 amdgpu 套件移除，不要重新開機，直接跑 UnrealEngine ，可以成功
但是重新開機後，一樣，回到原始安裝 scenario 1  的情境


# scenario 4

Ubuntu 20.04 安裝，使用系統預設的 kernel 版本， 使用 ppa:oibaf/graphics-drivers 的 amdgpu driver

sudo add-apt-repository ppa:oibaf/graphics-drivers 

參考 https://linuxconfig.org/amd-radeon-ubuntu-20-04-driver-installation 文件
glxinfo 及 vulkaninfo 皆正常，開啟 UnrealEngine 時，crash


以上就是試過，但是多少有些問題

# success 1

目前安裝沒有問題的方式

Ubuntu 20.04 安裝，使用系統預設的 kernel 版本，安裝 vulkan sdk ，及套件

參考 https://vulkan.lunarg.com/sdk/home#linux

<pre>
wget -qO - https://packages.lunarg.com/lunarg-signing-key-pub.asc | sudo apt-key add -
sudo wget -qO /etc/apt/sources.list.d/lunarg-vulkan-focal.list https://packages.lunarg.com/vulkan/lunarg-vulkan-focal.list
sudo apt update
sudo apt install vulkan-sdk
</pre>

使用 amdgpu pro driver 20.30  
https://www.amd.com/zh-hant/support/kb/release-notes/rn-amdgpu-unified-linux-20-30
但是安裝方式，請參考 Debian 文件，手動安裝 
https://wiki.debian.org/AMDGPUDriverOnStretchAndBuster2


我們再加上 amdgpu-pro-core_*.deb vulkan-amdgpu*.deb 也就是只有安裝這些 

<pre>
cd amdgpu-pro-20.30-1109583-ubuntu-20.04/
sudo dpkg -i amdgpu-dkms-firmware_*.deb
sudo dpkg -i amdgpu-core_*.deb amdgpu-dkms_*.deb amdgpu-pro-core_*.deb vulkan-amdgpu*.deb
</pre>

就這樣，重新開機，就可以了

# success 2 

Ubuntu 20.04 安裝後， 安裝 ppa:oibaf/graphics-drivers 的 amdgpu driver

sudo add-apt-repository ppa:oibaf/graphics-drivers 

然後 kernel 更新使用 ubuntu mainline 的 kernel ，對新的硬體支援比較快 ，可以參考 https://wiki.ubuntu.com/Kernel/MainlineBuilds

我目前先安裝 5.8.13 的版本， https://kernel.ubuntu.com/~kernel-ppa/mainline/?C=N;O=D

安裝後，重開機就可以了，沒有使用 amd 釋出的驅動程式好處是，不會被限制在特定版本的 kernel ，彈性比較好

ppa:oibaf/graphics-drivers 的更新也算是非常積極，後續新的硬體支援，穩定性應該可以提升比較快

<img src="https://lh3.googleusercontent.com/8AKRngJD2GG-YL7M3NNOh6-k6csDIZGWzBgzdwohj_k8JmzySgEkjlcP2H_41n09DHoP3JVEybyNt47X6bnn5gs-VYb54hpFbhfZNWlsEeul1XViKKK-T_AoXYXtEtpDUlxQPiQodtw=w800-h1045-p-k" />
