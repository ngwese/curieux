# notes

## aes67-linux-daemon

- build dependencies `sudo apt install clang cmake libboost-all-dev alsa-utils libasound2-dev linuxptp libavahi-client-dev libsystemd-dev`
- edit `build.sh` for daemon
  - `ENABLE_TESTS=OFF`
  - `WITH_STREAMER=OFF`
  - `WITH_SYSTEMD=ON`

### configuration

global aes67 daemon config

| parameter            | value      | notes |
| -------------------- | ---------- | ----- |
| TIC frame size @ 1FS | `48 - 1ms` |       |
| Initial sample rate  | `48 kHz`   |       |
| RTP base address     | `239.4.0.1` | the 239.4 was picked at random, if there are multiple hosts ensure they have different base addresses |


sources

| parameter              | value      | notes | 
| ---------------------- | ---------- | ----- |
| Max samples per packet | `48 - 1ms` | |
| Codec                  | L27 | |
