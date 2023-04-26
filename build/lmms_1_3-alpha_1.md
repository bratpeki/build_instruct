
All the compilation info is listed [here](https://github.com/LMMS/lmms/wiki/Compiling).

This doc is subject to change so this is the summary of what it says:

# Build system

You must have `cmake` (>3.3.0).

# Compilers

You must have one of these:

- `gcc`/`g++`(`c++11`)
- `clang`
- `mingw-w64`

# Libraries:

In the "Use" section, the things starting with `-D` are `cmake` flags.

| Type | Name (Version) | Description | Installation | Use |
| - | - | - | - | - |
| R | `Qt5` (>=5.6) | GUI toolkit | `pacman -S qt5-x11extras qt5-tools` | Graphics |
| R | `libsndfile` (>=1.0.26) | Reading and writing sound files | `pacman -S libsndfile` | Audio |
| R | `fftw3` | Fast fourier transform computing library | `pacman -S fftw` | Computation |
| R | `libsamplerate` | Sample rate convertor | `pacman -S libsamplerate` | Audio |
| | `libvorbis` | Vorbis file format family library | `pacman -S libvorbis` | OGG/Vorbis support, turned off with `-DWANT_OGGVORBIS=OFF` |
| | `libogg` | OGG Vorbis library | `pacman -S libogg` | OGG/Vorbis support, turned off with `-DWANT_OGGVORBIS=OFF` |
| | `wine` | Windows functionality emulator | `pacman -S wine` | VST support, turned off with `-DWANT_VST=OFF -DWANT_VST_32=OFF -DWANT_VST_64=OFF` |
| | `libstk` | Synthesis ToolKit | `pacman -S stk` | Audio processing, turned off with `-DWANT_STK=OFF` |
| | `libfluidsynth` | SoundFont (2) player | `pacman -S fluidsynth` | SoundFont playing, turned off with `-DWANT_SF2=OFF` |
| | `fltk` | X GUI | `pacman -S fltk` | Needed for `ZynAddSubFx`, `cmake` will check for it |
| | `jack` | JACK Audio Connection Kit | `pacman -S jack2` or `pacman -S pipewire-jack` | Turned off with `-DWANT_JACK=OFF` |
| * | `sdl` | Simple DirectMedia Library | `pacman -S sdl sdl-openglhq sdl-nokbgrab sdl-openglhq-nokbgrab sdl-git sdl2_compat12-git sdl12-compat-git sdl12-compat` | Turned off with `-DWANT_SDL=OFF` |
| * | `alsa` | Advanced Linux Sound Architecture | `pacman -S alsa-lib alsa-firmware`, if you're on PipeWire add `pipewire-alsa` | Turned off with `-DWANT_ALSA=OFF` |
| * | `libportaudio` | Audio interface library | `pacman -S portaudio` | Turned off with `-DWANT_PORTAUDIO=OFF` |
| * | `libsoundio` | Audio interface library | `pacman -S libsoundio` | Turned off with `-DWANT_SOUNDIO=OFF` |
| * | `sndio` | Audio and MIDI framework | `pacman -S sndio` | Turned off with `-DWANT_SNDIO=OFF` |
| | `perl` | Programming language | `pacman -S perl` | Compiling `swh` LADSPA plugins, turned off with `-DWANT_SWH=OFF` |
| | `perl` `XML::Parser` | Perl library | `cpan List::MoreUtils XML::Parser` | Compiling `swh` LADSPA plugins, turned off with `-DWANT_SWH=OFF` |

`R` - Required
`*` - At least one required

