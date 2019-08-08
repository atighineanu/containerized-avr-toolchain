# Build AVR tool chain inside containers
Have a look at `SmartGH/notes/ressources.md` to find upstream documentation.

## [WIP] Usage

Keep in mind: This is a work in progress.

The image is currently based on `alpine` and that means it should be linked
with `musl`. If this affects the avr tool chain, is still unknown to me.
Further testing has to be done.

### Building the container
```
podman build -t avr_toolchain:latest .
```
### Running
```
# run the container. This will drop you into a `sh` shell.
podman run -ti avr_toolchain:latest
# From here on, you are operating inside the container
# execute `run.sh`. This will curl binutils, gcc and avr-libc and `configure`
# and `make` the different projects, while also installing build-time
# requirments for gcc.
avr_toolchain $ ./run.sh
```