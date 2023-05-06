# OrangePi5-OpenCL
Make OpenCL work with OPi5 (tested with Armbian Jammy)
```
git clone https://github.com/bbaranoff/libmali-bin
sudo add-apt-repository ppa:liujianfeng1994/panfork-mesa
sudo add-apt-repository ppa:liujianfeng1994/rockchip-multimedia
sudo apt update
sudo apt dist-upgrade
sudo apt install mali-g610-firmware rockchip-multimedia-config
sudo apt install malirun

mesa-opencl-icd/jammy,now 23.0~panfork~csf~git221210.120202c6757~j+3 arm64  [installé]
libclc-14/jammy,jammy,now 1:14.0.0-1ubuntu1 all  [installé, automatique]
libclc-14-dev/jammy,jammy,now 1:14.0.0-1ubuntu1 all  [installé, automatique]
pocl-opencl-icd/jammy,now 1.8-3 arm64  [installé]

echo "libmali.so" > /etc/OpenCL/vendors/mali.icd
cp /etc/OpenCL/vendors/mali.icd /home/nirvana/miniforge3/etc/OpenCL/vendors/mali.icd
cd libmali-bin
cp libmali-valhall-g610-g6p0-x11-gbm.so /usr/lib/aarch64-linux-gnu
cd /usr/lib/aarch64-linux-gnu
ln -s libmali-valhall-g610-g6p0-x11-gbm.so libmali.so
apt install clinfo
clinfo
```
Good Luck
