
All the compilation info is listed [here](https://github.com/LMMS/lmms/wiki/Compiling).

This doc is subject to change so this is the summary of what it says:

# Build system

You must have `cmake` (>3.3.0).

# Compilers

You must have one of these:

- `gcc`/`g++`(`c++11`)
- `clang`
- `mingw-w64`

# Libraries

In the "Use" section, the things starting with `-D` are `cmake` flags.

| Type | Name (Version) | Installation | Use |
| - | - | - | - |
| R | `Qt5` (>=5.6) | `pacman -S qt5-x11extras qt5-tools` | Graphics |
| R | `libsndfile` (>=1.0.26) | `pacman -S libsndfile` | Audio |
| R | `fftw3` | `pacman -S fftw` | Computation |
| R | `libsamplerate` | `pacman -S libsamplerate` | Audio |
| | `libvorbis` | `pacman -S libvorbis` | OGG/Vorbis support, turned off with `-DWANT_OGGVORBIS=OFF` |
| | `libogg` | `pacman -S libogg` | OGG/Vorbis support, turned off with `-DWANT_OGGVORBIS=OFF` |
| | `wine` | `pacman -S wine` | VST support, turned off with `-DWANT_VST=OFF -DWANT_VST_32=OFF -DWANT_VST_64=OFF` |
| | `libstk` | `pacman -S stk` | Audio processing, turned off with `-DWANT_STK=OFF` |
| | `libfluidsynth` | `pacman -S fluidsynth` | SoundFont playing, turned off with `-DWANT_SF2=OFF` |
| | `fltk` | `pacman -S fltk` | Needed for `ZynAddSubFx`, `cmake` will check for it |
| | `jack` | `pacman -S jack2` or `pacman -S pipewire-jack` | Turned off with `-DWANT_JACK=OFF` |
| * | `sdl` | `pacman -S sdl sdl-openglhq sdl-nokbgrab sdl-openglhq-nokbgrab sdl-git sdl2_compat12-git sdl12-compat-git sdl12-compat` | Turned off with `-DWANT_SDL=OFF` |
| * | `alsa` | `pacman -S alsa-lib alsa-firmware`, if you're on PipeWire add `pipewire-alsa` | Turned off with `-DWANT_ALSA=OFF` |
| * | `libportaudio` | `pacman -S portaudio` | Turned off with `-DWANT_PORTAUDIO=OFF` |
| * | `libsoundio` | `pacman -S libsoundio` | Turned off with `-DWANT_SOUNDIO=OFF` |
| * | `sndio` | `pacman -S sndio` | Turned off with `-DWANT_SNDIO=OFF` |
| | `perl` | `pacman -S perl` | Compiling `swh` LADSPA plugins, turned off with `-DWANT_SWH=OFF` |
| | `perl` `XML::Parser` | `cpan List::MoreUtils XML::Parser` | Compiling `swh` LADSPA plugins, turned off with `-DWANT_SWH=OFF` |

# CMake flags

The value of each option is either ON or OFF.

| Option | Description | Default value |
| - | - | - |
| `WANT_ALSA` | Include ALSA (Advanced Linux Sound Architecture) support | ON |
| `WANT_CALF` | Include CALF LADSPA plugins | ON |
| `WANT_CAPS` | Include C* Audio Plugin Suite (LADSPA plugins) | ON |
| `WANT_CARLA` | Include Carla plugin | ON |
| `WANT_CMT`  |Include Computer Music Toolkit LADSPA plugins | ON |
| `WANT_JACK` | Include JACK (Jack Audio Connection Kit) support | ON |
| `WANT_WEAKJACK` | Loosely link JACK libraries | ON |
| `WANT_LV2` | Include Lv2 plugins | ON |
| `WANT_SUIL` | Include SUIL for LV2 plugin UIs | ON |
| `WANT_MP3LAME` | Include MP3/Lame support | ON |
| `WANT_OGGVORBIS` | Include OGG/Vorbis support | ON |
| `WANT_PULSEAUDIO` | Include PulseAudio support | ON |
| `WANT_PORTAUDIO` | Include PortAudio support | ON |
| `WANT_SNDIO` | Include sndio support | ON |
| `WANT_SOUNDIO` | Include libsoundio support | ON |
| `WANT_SDL` | Include SDL (Simple DirectMedia Layer) support | ON |
| `WANT_SF2` | Include SoundFont2 player plugin | ON |
| `WANT_GIG` | Include GIG player plugin | ON |
| `WANT_STK` | Include Stk (Synthesis Toolkit) support | ON |
| `WANT_SWH` | Include Steve Harris's LADSPA plugins | ON |
| `WANT_TAP` | Include Tom's Audio Processing LADSPA plugins | ON |
| `WANT_VST` | Include VST support | ON |
| `WANT_VST_32` | Include 32-bit VST support | ON |
| `WANT_VST_64` | Include 64-bit VST support | ON |
| `WANT_WINMM` | Include WinMM MIDI support | OFF |
| `WANT_DEBUG_FPE` | Debug floating point exceptions | OFF |
| `BUNDLE_QT_TRANSLATIONS` | Install Qt translation files for LMMS | OFF |

`R` - Required
`*` - At least one required

