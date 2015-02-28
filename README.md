# prd-bld

git clone https://github.com/01org/prd
cd prd

# Use .config from currently running kernel
cp /boot/config-`uname -r` .config

# Enable Drivers -> Block Devices -> "Persistent memory block device support"
cat ../prd-bld/prd-config-add.txt >> .config

make olddefconfig
make -j10
sudo make modules_install
sudo make install
