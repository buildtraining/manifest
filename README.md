# manifest
Pure Pixel
Getting Started
To build Pure Pixel from source, you'll need to be familiar with Git and Repo.

To initialize your local repository, use this command:

repo init -u https://github.com/buildtraining/manifest.git -b o81x
Then to sync source, use this command:

repo sync
After syncing is done, use these commands to build:

1.) . build/envsetup.sh
2.) brunch xxxx yyyy

xxxx= device name aka walleye
yyyy= build type (user,userdebug,eng)*

*if no build type is specified "user" is default

or

. build/envsetup.sh && brunch walleye userdebug
powered by S.i.X ROM

Setup to build Android from source instructions
Remove all traces of Java:
sudo apt-get remove openjdk-* icedtea-* icedtea6-*

Add OpenJDK7 PPA & Fetch:
sudo add-apt-repository ppa:openjdk-r/ppa && sudo apt-get update

Install all available updates:
sudo apt-get upgrade && sudo apt-get dist-upgrade

Install OpenJDK7 and Android dependencies:
sudo apt-get install adb

sudo apt-get install fastboot

sudo apt-get install openjdk-7-jdk

sudo apt-get install git

sudo apt-get install ccache

sudo apt-get install automake

sudo apt-get install lzop

sudo apt-get install bison

sudo apt-get install gperf

sudo apt-get install build-essential

sudo apt-get install zip

sudo apt-get install curl

sudo apt-get install zlib1g-dev

sudo apt-get install zlib1g-dev:i386

sudo apt-get install g++-multilib

sudo apt-get install python-networkx

sudo apt-get install libxml2-utils

sudo apt-get install bzip2

sudo apt-get install libbz2-dev

sudo apt-get install libbz2-1.0

sudo apt-get install libghc-bzlib-dev

sudo apt-get install squashfs-tools

sudo apt-get install pngcrush

sudo apt-get install schedtool

sudo apt-get install dpkg-dev

sudo apt-get install liblz4-tool

sudo apt-get install make

sudo apt-get install optipng

sudo apt-get install maven

sudo apt-get install python-mako

sudo apt-get install python3-mako

sudo apt-get install python

sudo apt-get install python3

sudo apt-get install syslinux-utils

sudo apt-get install flex

sudo apt-get install lib32ncurses5-dev

sudo apt-get install libxml2-utils

sudo apt-get install xsltproc

sudo apt-get install google-android-build-tools-installer

Remove unnecessary packages:
sudo apt-get autoremove

Make a user accessible folder, and add it to path:
mkdir /bin && echo "export PATH=/bin:$PATH" >> ~/.bashrc

Enable CCACHE:
echo "export USE_CCACHE=1" >> ~/.bashrc

Restart Bash:
source ~/.bashrc

Configure Git:
git config --global user.name "username"

git config --global user.email useremail@email.com

Enable Repo and put it in local $PATH folder:
curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo

Make a source folder for your ROM and initialize repo:
mkdir ~/purepixel

next

cd ~/purepixel

now

repo init -u https://github.com/buildtraining/manifest.git -b o81x

Sync Repo:
repo sync

if you need to force sync

repo sync --force-sync

Build the ROM:
prebuilts/misc/linux-x86/ccache/ccache -M 50G

. build/envsetup.sh && brunch shamu userdebug

or the long way

. build/envsetup.sh

lunch

pick your device number from menu

make -j4 otapackage

Find the ROM: out/target/product/ >> /romname.zip
Flash ROM & Enjoy
