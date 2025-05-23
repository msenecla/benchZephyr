# benchZephyr

## Install SDK

From: https://docs.zephyrproject.org/latest/develop/getting_started/index.html



## Bench ZSWatch

From https://github.com/ZSWatch/ZSWatch?tab=readme-ov-file#environment-compiling-and-running-the-code

```bash
git clone git@github.com:ZSWatch/ZSWatch.git
```

```bash
cd ZSWatch
git submodule update --init --recursive
cd app
west init -l .
west update
time west build app -p -b zswatch@5/nrf5340/cpuapp -- -DOVERLAY_CONFIG=boards/release.conf -DBOARD_ROOT=${PWD}/app
```

```bash
(.venv) zephyr@m4pro app % west build app -p -b zswatch@5/nrf5340/cpuapp -- -DOVERLAY_CONFIG=boards/release.conf -DBOARD_ROOT=${PWD}   

ERROR: source directory app does not exist

FATAL ERROR: refusing to proceed without --force due to above error
```

```bash
west build app -b zswatch_nrf5340_cpuapp@3 -- -DOVERLAY_CONFIG=boards/debug.conf -DBOARD_ROOT=${PWD}/app

ninja: build stopped: subcommand failed.
FATAL ERROR: command exited with status 1: /opt/homebrew/bin/cmake --build /Users/zephyr/testmartin/ZSWatch/build

```



| Platform                        |      |      |
| ------------------------------- | ---- | ---- |
| Macbook Pro M4 pro no Defender  |      |      |
| MacBook Pro Intel no Defender   |      |      |
| MacBook Pro Intel with Defender |      |      |



## Bench shell_module

from https://copilot.cloud.microsoft/?fromCode=cmcv2&redirectId=57EE0A71C0EF4C43B310CBC660A9411D&auth=2

```bash
source ~/zephyrproject/.venv/bin/activate
```


```bash
git clone https://github.com/zephyrproject-rtos/zephyr.git
cd zephyr
```


```bash
west init -m https://github.com/zephyrproject-rtos/zephyr
west update
west zephyr-export
```


```bash
cd samples/subsys/shell/shell_module
time west build -p -b nrf5340dk/nrf5340/cpuapp
```


| Platform                        |                                                              |      |
| ------------------------------- | ------------------------------------------------------------ | ---- |
| Macbook Pro M4 pro no Defender       | west build -b nrf5340dk/nrf5340/cpuapp 21.63s user 6.38s system 424% cpu 6.602 total |      |
| Macbook Air M? no Defender       | west build -p -b nrf5340dk/nrf5340/cpuapp  26,50s user 5,76s system 348% cpu 9,257 total |      |
| MacBook Pro Intel no Defender   |                                                              |      |
| MacBook Pro Intel with Defender | west build -p -b nrf5340dk/nrf5340/cpuapp 101.03s user 28.80s system 110% cpu 1:57.44 total |      |

