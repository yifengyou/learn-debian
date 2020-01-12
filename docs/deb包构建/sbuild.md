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

deb http://mirrors.tencent.com/ubuntu bionic partner
deb-src http://mirrors.tencent.com/ubuntu bionic partner

deb http://mirrors.tencent.com/ubuntu bionic-security main restricted
deb-src http://mirrors.tencent.com/ubuntu bionic-security main restricted
deb http://mirrors.tencent.com/ubuntu bionic-security universe
deb-src http://mirrors.tencent.com/ubuntu bionic-security universe
deb http://mirrors.tencent.com/ubuntu bionic-security multiverse
deb-src http://security.ubuntu.com/ubuntu bionic-security multiverse

```


## sbuild安装

```
sudo apt-get install sbuild -y
````

sbuild包介绍

```
Package: sbuild
Architecture: all
Version: 0.75.0-1ubuntu1
Priority: extra
Section: devel
Origin: Ubuntu
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
Original-Maintainer: Debian buildd-tools Developers <buildd-tools-devel@lists.alioth.debian.org>
Bugs: https://bugs.launchpad.net/ubuntu/+filebug
Installed-Size: 275
Depends: adduser, libsbuild-perl (= 0.75.0-1ubuntu1), perl:any
Recommends: debootstrap, schroot (>= 1.6.0), autopkgtest (>= 4.0.4)
Suggests: deborphan, wget, kmod
Filename: pool/main/s/sbuild/sbuild_0.75.0-1ubuntu1_all.deb
Size: 85732
MD5sum: d4511899b5a4837aca6c26f6acccdd5e
SHA1: 47785cdf3e99e5b55aa6847c8eca69958166fa23
SHA256: 4a99a4a5945342ea0a8883c8b2c51b7a08ae66552e7eadaba287c79fd625875e
Description-en: Tool for building Debian binary packages from Debian sources
 The sbuild suite of programs (buildd and sbuild) are used to build
 binary packages from source packages.  sbuild does the actual package
 building.
 .
 sbuild uses chroots to build packages, which act as virtual, minimal
 operating system installations dedicated to package building.  This
 means that a number of environments may be used for building
 simultaneously on the same machines, for example stable, testing,
 unstable and experimental.  When coupled with schroot to create
 snapshots of chroots, sbuild may be used to build many packages in
 parallel.  A chroot environment allows packages to be built in a
 controlled, clean environment.  sbuild installs only essential and
 build-essential packages, plus those in the package build
 dependencies.
Description-md5: 9e15ceda32607c62e78e4f4d946f038e
Supported: 5y

```

sbuild包文件列表
```
/etc/sbuild/sbuild.conf

/usr/bin/sbuild
/usr/bin/sbuild-abort
/usr/bin/sbuild-apt
/usr/bin/sbuild-checkpackages
/usr/bin/sbuild-clean
/usr/bin/sbuild-distupgrade
/usr/bin/sbuild-hold
/usr/bin/sbuild-shell
/usr/bin/sbuild-unhold
/usr/bin/sbuild-update
/usr/bin/sbuild-upgrade

/usr/sbin/sbuild-adduser
/usr/sbin/sbuild-createchroot
/usr/sbin/sbuild-destroychroot

/usr/share/doc/sbuild/NEWS.Debian.gz
/usr/share/doc/sbuild/README.Debian
/usr/share/doc/sbuild/README.bins

/usr/share/doc/sbuild/configs/README
/usr/share/doc/sbuild/configs/ref-oldstable
/usr/share/doc/sbuild/configs/ref-stable
/usr/share/doc/sbuild/configs/ref-testing
/usr/share/doc/sbuild/configs/ref-unstable
/usr/share/doc/sbuild/copyright

/usr/share/doc/sbuild/examples/example.sbuildrc
/usr/share/doc/sbuild/examples/sbuild-update-all

/usr/share/man/man1/sbuild-abort.1.gz
/usr/share/man/man1/sbuild-apt.1.gz
/usr/share/man/man1/sbuild-checkpackages.1.gz
/usr/share/man/man1/sbuild-debian-developer-setup.1.gz
/usr/share/man/man1/sbuild-hold.1.gz
/usr/share/man/man1/sbuild-shell.1.gz
/usr/share/man/man1/sbuild-update.1.gz
/usr/share/man/man1/sbuild.1.gz

/usr/share/man/man5/sbuild.conf.5.gz

/usr/share/man/man7/sbuild-setup.7.gz

/usr/share/man/man8/sbuild-adduser.8.gz
/usr/share/man/man8/sbuild-createchroot.8.gz
/usr/share/man/man8/sbuild-destroychroot.8.gz

/usr/share/sbuild/create-chroot
/usr/share/sbuild/dobuildlog

/var/lib/sbuild/apt-keys
/var/lib/sbuild/build

/usr/share/doc/sbuild/changelog.Debian.gz
/usr/share/man/man1/sbuild-clean.1.gz
/usr/share/man/man1/sbuild-distupgrade.1.gz
/usr/share/man/man1/sbuild-unhold.1.gz
/usr/share/man/man1/sbuild-upgrade.1.gz

```



export LANG='en_US.utf8'
export LC_ALL='C.UTF-8'

APT_CONFIG=/var/lib/sbuild/apt.conf
HOME=/sbuild-nonexistent
LANG=en_US.utf8
LC_ALL=C.UTF-8
LOGNAME=tbuild
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games
SCHROOT_ALIAS_NAME=bionic-amd64-sbuild
SCHROOT_CHROOT_NAME=bionic-amd64-sbuild
SCHROOT_COMMAND=env
SCHROOT_GID=1001
SCHROOT_GROUP=tbuild
SCHROOT_SESSION_ID=bionic-amd64-sbuild-de6ff4ac-a542-4892-a954-61e929d49700
SCHROOT_UID=1000
SCHROOT_USER=tbuild
SHELL=/bin/sh
USER=tbuild


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

deb http://mirrors.tencent.com/ubuntu bionic-security main restricted
deb-src http://mirrors.tencent.com/ubuntu bionic-security main restricted
deb http://mirrors.tencent.com/ubuntu bionic-security universe
deb-src http://mirrors.tencent.com/ubuntu bionic-security universe
deb http://mirrors.tencent.com/ubuntu bionic-security multiverse
deb-src http://security.ubuntu.com/ubuntu bionic-security multiverse
```



## 参考

---
