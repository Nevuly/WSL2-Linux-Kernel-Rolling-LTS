# Rolling Release LTS Kernel for WSL2

[![LTS Kernel CI](https://img.shields.io/github/actions/workflow/status/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/build.yml?label=github%20actions%20build&logo=github-actions&logoColor=%23FFFFFF&style=for-the-badge&labelColor=%23000000)](https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/actions/workflows/build.yml)
[![Release](https://img.shields.io/github/v/release/Nevuly/WSL2-Linux-Kernel-Rolling-LTS?display_name=tag&label=LATEST&logo=Linux&logoColor=%23FFFFFF&style=for-the-badge&labelColor=%23000000)](https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/releases/latest)

Maintainer: Yang Jeong Hun (Nevuly)

## Current Kernel Status

| Kernel Version | Status |
|:--------------:|:------:|
| [Linux 6.6.x][wsl2-kernel-6.6] | LTS Support |

## Introduction

The [WSL2-Linux-Kernel-Rolling-LTS][wsl2-kernel-rolling-lts] repo contains the latest LTS kernel source code and
configuration files for the [WSL2][about-wsl2].

This kernel is automatically built via [Github Actions][gh-actions] CI whenever a [newer LTS kernel is released][kernel-lts].

## Reporting Bugs

If you discover an issue relating to WSL or the WSL2 kernel, please report it on
the [Issues tab][issue].

## Feature Requests

If you want to fix a bug or add new features, Please use the [Pull Request][pr].

## Build Instructions

Instructions for building WSL2 kernel with an Arch Linux distribution are
as follows:

1. Install the build dependencies (Arch Linux):  
   `$ sudo pacman -S aarch64-linux-gnu-gcc bc bison curl flex gcc git pahole python unzip wget zip`

2. Build the kernel using the WSL2 kernel configuration (x86):  
   `$ make KCONFIG_CONFIG=arch/x86/configs/config-wsl-x86`

3. Build the kernel using the WSL2 kernel configuration (arm64):  
   `$ export ARCH=arm64 && export CROSS_COMPILE=aarch64-linux-gnu-`  
   `$ make KCONFIG_CONFIG=arch/arm64/configs/config-wsl-arm64`

4. Save the module to a separate folder (Optional. Only for local build):  
   `$ sudo make modules_install`

## Install Instructions

Please see the documentation on the [.wslconfig configuration
file][install-inst] for information on using a custom built kernel.

## Credits
 * The Linux community who created a awesome kernel.
 * Microsoft which produced WSL2 and dxgkrnl patches.
 * [justinkb (Paul Mulders)][justinkb] helped when docker desktop can't run correctly.

[wsl2-kernel-6.6]: https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/tree/wsl-6.6-lts
[wsl2-kernel-rolling-lts]: https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS
[about-wsl2]: https://docs.microsoft.com/en-us/windows/wsl/about#what-is-wsl-2
[gh-actions]: https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/actions
[kernel-lts]: https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git/log/?h=linux-6.6.y
[issue]: https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/issues
[pr]: https://github.com/Nevuly/WSL2-Linux-Kernel-Rolling-LTS/pulls
[install-inst]: https://docs.microsoft.com/en-us/windows/wsl/wsl-config#configure-global-options-with-wslconfig
[justinkb]: https://github.com/justinkb