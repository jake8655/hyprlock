# hyprlock
Hyprland's simple, yet multi-threaded and GPU-accelerated screen locking utility.

## Features
 - uses the secure ext-session-lock protocol
 - full support for fractional-scale
 - fully GPU accelerated
 - multi-threaded resource acquisition for no hitches

## How it looks

![](https://i.ibb.co/8Bd98BP/20240220-00h12m46s.png)

## Docs / Configuration
[See the wiki](https://wiki.hyprland.org/Hypr-Ecosystem/hyprlock/)

## Arch install
```sh
pacman -S hyprlock # binary x86 tagged release
# or
yay -S hyprlock-git # compiles from latest source
```

## Building

### Deps
You need the following dependencies
- wayland-client
- wayland-protocols
- mesa
- hyprwayland-scanner

And the development libraries for the following
- cairo
- libdrm
- pango
- xkbcommon
- pam
- hyprlang
- hyprutils
- hyprgraphics
- libmagic (file-devel on Fedora)

Development libraries are usually suffixed with `-devel` or `-dev` in most distro repos.

You also need to install `mesa-libgbm-devel` on some distros like RPM based ones where its not
bundled with the mesa package.

### Building

Building:
```sh
cmake --no-warn-unused-cli -DCMAKE_BUILD_TYPE:STRING=Release -S . -B ./build
cmake --build ./build --config Release --target hyprlock -j`nproc 2>/dev/null || getconf _NPROCESSORS_CONF`
```

Installation:
```sh
sudo cmake --install build
```
