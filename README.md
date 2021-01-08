# OpenWrt packages feed

## Description

This is the OpenWrt "packages"-feed containing community-maintained build scripts, options and patches for applications, modules and libraries used within OpenWrt.

Installation of pre-built packages is handled directly by the **opkg** utility within your running OpenWrt system or by using the [OpenWrt SDK](https://openwrt.org/docs/guide-developer/using_the_sdk) on a build system.

## Usage

This repository is intended to be layered on-top of an OpenWrt buildroot. If you do not have an OpenWrt buildroot installed, see the documentation at: [OpenWrt Buildroot – Installation](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem) on the OpenWrt support site.

This feed is enabled by default. To install all its package definitions, run:
```
./scripts/feeds update packages
./scripts/feeds install -a -p packages
```

In order to use this package feed one must edit `feeds.conf.default` and replace line of "packages" repo with
```
src-git https://github.com/eugeneai/openwrt-packages.git
```
then if a build SDK is used 
```
./scripts/feeds update -a 
./scripts/feeds install frr
make
```

The build will fail as base-dir is not built and cryptography keys were not issued.  Copy built modules `from bin/.../packages` to `packages` directory of Image Builder.

## License

See [LICENSE](LICENSE) file.
 
## Package Guidelines

See [CONTRIBUTING.md](CONTRIBUTING.md) file.

