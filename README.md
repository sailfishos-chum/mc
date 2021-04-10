# Midnight commander RPM for Sailfish OS


### Installation
Hopefully soon at openrepos.


### Build

# install the [Platform SDK](https://sailfishos.org/wiki/Platform_Development).
Also install the tooling and the target(s) that you need.

# open the chroot of the SDK:
```shell
  $ /srv/mer/sdks/sfossdk/mer-sdk-chroot
```

# enter ScratchBox2 in the target of your preference:
```shell
  $ sb2 -t SailfishOS-aarch64
  $ sb2 -t SailfishOS-armv7hl
  $ sb2 -t SailfishOS-i486
```

# cd to the directory of this repo:
```shell
  $ cd RPMS/slang/
```

# enter Scratchbox2 and run rpmbuild for building the "dumb" way:
```shell
  $ rpmbuild --define "_topdir `pwd`" --define "_sourcedir `pwd`" -bb *.spec
```



## Installing extra packages
# enter ScratchBox2 root shell in sdk-install mode for installing packages that are needed to build:
```shell
  $ sb2 -t SailfishOS-aarch64 -m sdk-install -R
  $ sb2 -t SailfishOS-armv7hl -m sdk-install -R
  $ sb2 -t SailfishOS-i486 -m sdk-install -R
```

You can now use zypper to install a package, for example make:
```shell
  # zypper install make
```

Or use rpm itself to install a local package
```shell
  # rpm -Uvh RPMS/armv7hl/packagename.rpm
```

After installing packages, exit Scratchbox2 and enter Scratchbox2 in the usual way to start the build.
