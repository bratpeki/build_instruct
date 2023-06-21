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

# My build setup

```sh

python waf configure --libjack=weak --ho-phone-home --optimize --with-backends=alsa,dummy,jack,pulseaudio
python waf

```
