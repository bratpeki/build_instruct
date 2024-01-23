Very little information is available.
Most of it is [here](https://ardour.org/building_linux.html).

# Prerequisites

You need the following:

- `gcc`/`g++` (>4.3)
- `git`
- `python` (>2.6)
- `JACK1` (>0.121), if you want JACK support

# Libraries

Since the documentation calls for the libraries by names, and there are **many**, I'll leave the ones stated by the AUR.

If I don't name the exact version of the program, consider getting any version released after Ardour 6.9 was released, which is August 13th, 2021.

| Type | Name | Alternatives | Use |
| - | - | - | - |
| R | `atkmm` | | |
| R | `cairo` | `cairo-git`, `cairo-minimal`, `cairo-glesv2-bin`, `cairo-glesv3-bin` | |
| R | `cairomm` | | |
| R | `fontconfig` | `fontconfig-srb`, `fontconfig-minimal-git`, `fontconfig-git`, `fontconfig-ubuntu` | |
| R | `gdk-pixbuf2` | `gdk-pixbuf2-git` | |
| R | `gcc-libs` | `gccrs-libs-git`, `gcc-libs-git`, `gcc11-libs` | |
| R | `glibc` | `glibc-force-mmap`, `lib32-glibc-force-mmap`, `glibc-minimal-git`, `glibc-linux4`, `glibc-git`, `glibc-widevine` | |
| R | `glibmm` | | |
| R | `gtkmm` | | |
| R | `libx11` | `libx11-git` | |
| R | `libxml2` | `libxml2-git` | |
| R | `pangomm` | | |
| R | `soundtouch` | `soundtouch-git` | |
| R | `taglib` | `taglib-git` | |
| R | `atk` | `atk-git`, `at-spi2-core` | |
| R | `aubio` | | |
| R | `boost` | `boost-git` | |
| R | `cppunit` | | |
| R | `curl` | `curl-minimal-git`, `curl-git`, `curl-quiche-git`, `curl-http3-ngtcp2` | |
| R | `dbus` | `dbus-elogind`, `dbus-nosystemd-minimal-git`, `dbus-nosystemd`, `dbus-x11`, `dbus-xdg-docs`, `dbus-git`, `dbus-selinux` | |
| R | `doxygen` | `doxygen-git`, `doxygen-clang` | |
| R | `fftw` | `fftw-amd` | |
| R | `flac` | `flac-nodocs-git`, `flac-minimal-git`, `flac-git` | |
| R | `fluidsynth` | `fluidsynth-git` | |
| R | `freetype2` | `freetype2-minimal-git`, `freetype2-ttmetrics`, `freetype2-git`, `freetype2-v35`, `freetype2-infinality-remix`, `freetype2-ultimate5` | |
| R | `git` | `git-vfs`, `git-run-command-patch-git`, `git-git`, `git-fc` | |
| R | `glib2` | `glib2-nodocs-git`, `glib2-selinux`, `glib2-git`, `glib2-patched-thumbnailer` | |
| R | `graphviz` | | |
| R | `gtk2` | `gtk2-git`, `gtk2-minimal-git`, `gtk2-maemo`, `gtk2-patched-filechooser-icon-view` | |
| R | `harfbuzz` | `harfbuzz-git`, `harfbuzz-minimal-git` | |
| R | `itstool` | | |
| R | `libarchive` | `libarchive-git` | | |
| R | `liblo` | `liblo-git`, `liblo-ipv6` | | |
| R | `liblrdf` | | | |
| R | `libltc` | | | |
| R | `libogg` | `libogg-git` | |
| R | `libpulse` | `libpulse-bluedio`, `pulseaudio-dummy`, `libpulse-nosystemd-git`, `libpulse-nosystemd`, `libpulse-nosystemd-minimal-git`, `pulseaudio-git` | |
| R | `libsamplerate` | `libsamplerate-minimal-git`, `libsamplerate-git` | |
| R | `libsndfile` | `libsndfile-minimal-git`, `libsndfile-git` | |
| R | `libusb` | `libusb-git` | |
| R | `libwebsockets` | | |
| R | `lilv` | `lilv-git` | |
| R | `lv2` | `lv2-git` | |
| R | `pango` | `pango-minimal-git`, `pango-git`, `gtk4-git` | |
| R | `readline` | `readline-athame-git`, `readline-git` | |
| R | `rubberband` | | Sample time-stretching |
| R | `serd` | `serd-git` | |
| R | `sord` | `sord-git` | |
| R | `sratom` | `sratom-git` | |
| R | `suil` | `suil-git` | |
| R | `vamp-plugin-sdk` | | |
| O | `harvid` | | Video timeline |
| O | `libwebsockets` | | WebSockets control support |
| O | `non-session-manager` | `non-daw-git`, `new-session-manager` | Session management |
| O | `xjadeo` | | Video monitoring |

`R` - Required<br>
`O` - Optional

Libs from `atkmm` to `taglib` are software dependencies.<br>
Libs from `atk` to `vamp-plugin-sdk` are `make` dependencies.

You can install the libs with:

```sh
sudo pacman -S \
  atkmm cairo cairomm fontconfig gdk-pixbuf2 gcc-libs \
  glibc glibmm gtkmm libx11 libxml2 pangomm soundtouch \
  taglib atk aubio boost cppunit curl dbus doxygen fftw \
  flac fluidsynth freetype2 git glib2 graphviz gtk2 \
  harfbuzz itstool libarchive liblo liblrdf libltc \
  libogg libpulse libsamplerate libsndfile libusb \
  libwebsockets lilv lv2 pango readline rubberband \
  serd sord sratom suil vamp-plugin-sdk
```

# My build setup

```sh
python waf configure --libjack=weak --no-phone-home --optimize --with-backends=alsa,dummy,jack,pulseaudio
python waf
```
All the `WAF` commands are available under `python waf --help`.
