# sbuild

apt-get source pdf2djvu

sudo apt-get install sbuild

sudo sbuild-adduser $LOGNAME
groups # find current normal user


vi ~/.sbuildrc

$build_arch_all=1;
$build_source =1;
$distribution='bionic';


sudo sbuild-createchroot --make-sbuild-tarball=/var/lib/sbuild/stretch-amd64.tar.gz stretch `mktemp -d ` http://ftp.uni-hannover.de/debian/debian

sudo sbuild-createchroot --make-sbuild-tarball=/var/lib/sbuild/bionic-amd64.tar.gz bionic `mktemp -d ` http://mirrors.tencent.com/ubuntu

sudo sbuild-update -udcar bionic-amd64-sbuild


sudo sbuild-createchroot --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic main restricted\n deb http://mirrors.tencent.com/ubuntu/ bionic-updates main restricted\n deb http://mirrors.tencent.com/ubuntu/ bionic universe\n deb http://mirrors.tencent.com/ubuntu/ bionic-updates universe\n deb http://mirrors.tencent.com/ubuntu/ bionic multiverse\n deb http://mirrors.tencent.com/ubuntu/ bionic-updates multiverse\n deb http://mirrors.tencent.com/ubuntu/ bionic-backports main restricted universe multiverse" --make-sbuild-tarball=/var/lib/sbuild/bionic-amd64.tar.gz bionic `mktemp -d ` http://mirrors.tencent.com/ubuntu


ls -alh /var/lib/sbuild


schroot -l

sudo schroot -d / -c source:bionic-amd64-sbuild apt-get install eatmydata


sudo sbuild-createchroot --arch=arm64 --debootstrap=qemu-debootstrap --make-sbuild-tarball=/var/lib/sbuild/bionic-amd64.tar.gz bionic `mktemp -d` http://mirrors.tencent.com/ubuntu



sudo rm -rf /var/lib/sbuild/bionic-amd64.tar.gz
sudo rm -rf /etc/schroot/chroot.d/bionic-amd64-sbuild-*
sudo sbuild-createchroot  --include=apt-utils,vim  --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic main restricted"  --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic-updates main restricted" --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic universe" --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic-updates universe" --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic multiverse" --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic-updates multiverse" --extra-repository="deb http://mirrors.tencent.com/ubuntu/ bionic-backports main restricted universe multiverse" --make-sbuild-tarball=/var/lib/sbuild/bionic-amd64.tar.gz   bionic   `mktemp -d ` http://mirrors.tencent.com/ubuntu

sudo schroot -d / -c source:bionic-amd64-sbuild cat /etc/apt/sources.list




sudo rm -rf /var/lib/sbuild/bionic-amd64.tar.gz
sudo rm -rf /etc/schroot/chroot.d/bionic-amd64-sbuild-*
sudo sbuild-createchroot  --include=apt-utils,vim   --make-sbuild-tarball=/var/lib/sbuild/bionic-amd64.tar.gz   bionic   `mktemp -d ` http://mirrors.tencent.com/ubuntu

```
deb http://mirrors.tencent.com/ubuntu/ bionic main restricted
deb-src http://mirrors.tencent.com/ubuntu/ bionic main restricted

deb http://mirrors.tencent.com/ubuntu/ bionic-updates main restricted
deb-src http://mirrors.tencent.com/ubuntu/ bionic-updates main restricted

deb http://mirrors.tencent.com/ubuntu/ bionic universe
deb-src http://mirrors.tencent.com/ubuntu/ bionic universe
deb http://mirrors.tencent.com/ubuntu/ bionic-updates universe
deb-src http://mirrors.tencent.com/ubuntu/ bionic-updates universe

deb http://mirrors.tencent.com/ubuntu/ bionic multiverse
deb-src http://mirrors.tencent.com/ubuntu/ bionic multiverse
deb http://mirrors.tencent.com/ubuntu/ bionic-updates multiverse
deb-src http://mirrors.tencent.com/ubuntu/ bionic-updates multiverse

deb http://mirrors.tencent.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.tencent.com/ubuntu/ bionic-backports main restricted universe multiverse

```

---
