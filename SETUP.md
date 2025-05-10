# setup

## initial

from a minimal install of debian bookworm, setup `sudo`

* `su apt install sudo`
* `su usermod -aG sudo <you>`

once added to the `sudo` group, log out, then in to pickup the group
change

## packages

* `sudo apt-get install libevdev-dev liblo-dev libudev-dev libasound2-dev libsndfile1-dev libjack-dev`
* `sudo apt install --no-install-recommends jackd2 libjack-jackd2-dev`
* `sudo apt install git cmake ninja-build clang flex bison libtool automake autoconf gdb`
* `sudo apt install sudo avahi-daemon`


## kernel

* `sudo apt-get install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison`

clone the stable rt tree from kernel.org or a mirror:
* `https://git.kernel.org/pub/scm/linux/kernel/git/rt/linux-stable-rt.git`
* `https://kernel.googlesource.com/pub/scm/linux/kernel/git/rt/linux-stable-rt.git`

_TODO: document, local name, full preempt, 1000HZ settings, removal of embedded certs`

* `make aiop_defconfig`
* `make -j3 && make -j3 modules`
* `sudo make INSTALL_MOD_STRIP=1 modules_install`
* `sudo make install`
