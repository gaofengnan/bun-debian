![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/gaofengnan/bun-debian/total)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/gaofengnan/bun-debian/latest/total)
![GitHub Release](https://img.shields.io/github/v/release/gaofengnan/bun-debian)
![GitHub Release Date](https://img.shields.io/github/release-date/gaofengnan/bun-debian)

<h1>
   <p align="center">
     <a href="https://github.com/oven-sh/bun/"><img src="https://github.com/gaofengnan/bun-debian/blob/main/bun-logo.png" alt="Bun Logo" width="128" style="margin-right: 20px"></a>
     <a href="https://www.debian.org/"><img src="https://github.com/gaofengnan/bun-debian/blob/main/debian-logo.png" alt="Debian Logo" width="104" style="margin-left: 20px"></a>
     <br>Bun for Debian
   </p>
</h1>
<p align="center">
 👻 Bun is an all-in-one toolkit for JavaScript and TypeScript apps. It ships as a single executable called bun.
</p>

# Bun for Debian

> Fork of [dariogriffo/bun-debian](https://github.com/dariogriffo/bun-debian) (MIT); the original packaging is by Dario Griffo. Served at [deb.gaofn.xyz](https://deb.gaofn.xyz) for Debian 12 (bookworm) and 13 (trixie).

This repository contains build scripts to produce the _unofficial_ Debian packages
(.deb) for [Bun](https://github.com/oven-sh/bun) hosted at [deb.gaofn.xyz](https://deb.gaofn.xyz)

Currently supported debian distros are:
- Bookworm
- Trixie
- Forky
- Sid

This is an unofficial community project to provide a package that's easy to
install on Debian. If you're looking for the Bun source code, see
[bun](https://github.com/oven-sh/bun).

## Install/Update

### The Debian way

```sh
sudo install -d -m 0755 /etc/apt/keyrings
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.gpg -o /etc/apt/keyrings/deb.gaofn.xyz.gpg
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.sources -o /etc/apt/sources.list.d/deb.gaofn.xyz.sources
# Debian 12 (bookworm): fetch deb.gaofn.xyz-bookworm.sources instead
sudo apt update
sudo apt install bun
```

This gives you both the `bun` and `bunx` commands. As upstream does, `bunx` is a
symlink to the same binary; bun switches to `bun x` when invoked under that name.

If you want you can also install bun-profile as an alternative:
```sh
sudo apt install bun-profile
```

Then chose which one you want to use as default:
```sh
sudo update-alternatives --config bun
```

### Manual Installation

1. Download the .deb package for your Debian version available on
   the [Releases](https://github.com/gaofengnan/bun-debian/releases) page.
2. Install the downloaded .deb package.

```sh
sudo dpkg -i <filename>.deb
```
## Updating

To update to a new version, just follow any of the installation methods above. There's no need to uninstall the old version; it will be updated correctly.

## Contributing

I want to have an easy-to-install Bun package for Debian, so I'm doing what
I can to make it happen.
If you want to test locally, you should be able to run
[build_bun_debian.sh](https://github.com/gaofengnan/bun-debian/blob/main/build_bun_debian.sh)
on your own Debian system, only requirement is docker.

## Roadmap

- [x] Produce a .deb package on GitHub Releases
- [x] Set up a debian mirror for easier updates

## Disclaimer

- This repo is not open for issues related to bun. This repo is only for _unofficial_ Debian packaging.
- This repository is based on the amazing work of [Mike Kasberg](https://github.com/mkasberg) and his [Bun Ubuntu](https://github.com/mkasberg/ghostty-ubuntu) packages
