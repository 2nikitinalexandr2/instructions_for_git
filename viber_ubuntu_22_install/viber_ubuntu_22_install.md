```
wget https://download.cdn.viber.com/cdn/desktop/Linux/viber.deb
sudo apt install ./viber.deb
rm -rf viber.deb
```
# install the old, yet compatible with viber, openssl libs,
# to remove the "No connection" error at client startup
```
DEV=libssl-dev_1.1.1f-1ubuntu2_amd64.deb
NON_DEV=libssl1.1_1.1.1f-1ubuntu2_amd64.deb
wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/$DEV
wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/$NON_DEV
sudo apt install ./$DEV ./$NON_DEV
rm -rf $DEV $NON_DEV
```
* источник https://askubuntu.com/questions/1403319/viber-no-connection-on-ubuntu-22-04-even-i-have-an-internet