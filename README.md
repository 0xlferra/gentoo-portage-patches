# gentoo-portage-patches

User patches for Portage (`/etc/portage/patches`), shared between my Gentoo
machines. This repository is meant to be cloned directly as
`/etc/portage/patches`.

Portage applies every `*.patch`/`*.diff` file found in
`<category>/<PN>`, `<category>/<P>` or `<category>/<PF>` (each optionally
with `:<SLOT>`); subdirectories are ignored. A directory without a version
applies to **every** version of the package on **every** machine.

## Patches

| Package | Patch | Why |
|---|---|---|
| `app-emulation/fs-uae` | `fs-uae-3.2.35-gcc16-std-numbers.patch` | Rename `numbers` to avoid clashing with `std::numbers` under GCC 16 |
| `dev-cpp/glibmm-2.66.8` | `glibmm-2.66.8-gdbusactiongroup-emblem-final-types.patch` | Build giomm-2.4 (SLOT 2) against glib >= 2.89.2 (final types) |
| `dev-lang/python:2.7` | `python-2.7.18-fix-tcl-unichar-cast.patch` | Explicit `Tcl_UniChar` casts in `_tkinter` (Gentoo bug #921571) |
| `games-fps/yamagi-quake2-8.70` | `0001-allow-shlib-undefined.patch` | Add `--allow-shlib-undefined` to the link flags |
| `kde-plasma/xdg-desktop-portal-kde` | `xdg-desktop-portal-kde-restore-shortcuts-on-session-creation.patch` | Revert upstream 0d743a71: global shortcuts of Chromium/Electron apps die from the 2nd launch |
| `media-gfx/blender-5.2.2` | `eigen.patch`, `octree-eigen.patch`, `track_region.patch` | Build against current Eigen (`jacobiSvd` API) |
| `media-gfx/blender-5.2.2` | `blender-5.2.0-wayland-icon-slot.patch` | Use the slotted icon name (`blender-5.2.svg`) |
| `media-libs/libcaca` | `glut.patch` | Link `-lGL` in the GLUT configure checks |
| `media-video/ffmpeg` | `ffmpeg-4.4.3-opencl-parallel-gmake-fix.patch` | OpenCL parallel make fix (Gentoo bug #782553) |
| `net-misc/freerdp-3.32.1` | `freerdp-socks5-hostname-check.patch` | `/proxy:socks5` silently failing (`\|\|` vs `&&` in `socks_proxy_connect`) |
| `net-misc/openssh` | `sshkey.patch` | Lower `SSH_RSA_MINIMUM_MODULUS_SIZE` to 768 bits for legacy devices |
| `sys-kernel/genkernel` | `genkernel-overlay-wins-dedupe.patch` | `cpio -i -u` in the dedupe step, so `INITRAMFS_OVERLAY` files really override genkernel's own |
