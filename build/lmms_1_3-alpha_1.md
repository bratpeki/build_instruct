
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

| Type | Name (Version) | Description | Installation |
| - | - | - | - |
| R | `Qt5` (>=5.6) | GUI toolkit | `pacman -S qt5-x11extras qt5-tools` |
| R | `libsndfile` (>=1.0.26) | Reading and writing sound files | `pacman -S libsndfile` |
| R | `fftw3` | Fast fourier transform computing library | `pacman -S fftw` |
| R | `libsamplerate` | Sample rate convertor | `pacman -S libsamplerate` |
| | `libvorbis` | Vorbis file format family library | `pacman -S libvorbis` |
| | `libogg` | OGG Vorbis library | `pacman -S libogg` |
| | `wine` | VST support wrapper | `pacman -S wine` |
| | `libstk` | Synthesis ToolKit | `pacman -S stk` |
| | `libfluidsynth` | SoundFont (2) player | `pacman -S fluidsynth` |
| | `fltk` | X GUI | `pacman -S fltk` |
| | `jack` | JACK Audio Connection Kit | `pacman -S jack2` or `pacman -S pipewire-jack` |
| * | `sdl` | Simple DirectMedia Library | `pacman -S sdl sdl-openglhq sdl-nokbgrab sdl-openglhq-nokbgrab sdl-git sdl2_compat12-git sdl12-compat-git sdl12-compat` |
| * | `alsa` | Advanced Linux Sound Architecture | `pacman -S alsa-lib alsa-firmware`, if you're on PipeWire add `pipewire-alsa` |
| * | `libportaudio` | Audio interface library | `pacman -S portaudio` |
| * | `libsoundio` | Audio interface library | `pacman -S libsoundio` |
| | `perl` | Programming language | `pacman -S perl` |
| | `perl` `XML::Parser` | Perl library | `cpan XML::Parser` |

`R` - Required
`*` - At least one required

