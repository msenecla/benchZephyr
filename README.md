# benchZephyr

Install SDK

From: https://docs.zephyrproject.org/latest/develop/getting_started/index.html



Bench shell_module

from https://copilot.cloud.microsoft/?fromCode=cmcv2&redirectId=57EE0A71C0EF4C43B310CBC660A9411D&auth=2

```
source ~/zephyrproject/.venv/bin/activate
```


```
git clone https://github.com/zephyrproject-rtos/zephyr.git
cd zephyr
```


```
west init -m https://github.com/zephyrproject-rtos/zephyr
west update
west zephyr-export
```


```
cd samples/subsys/shell/shell_module
time west build -p -b nrf5340dk/nrf5340/cpuapp
```


| Platform           |                                                              |      |
| ------------------ | ------------------------------------------------------------ | ---- |
| Macbook Pro M4 pro | west build -b nrf5340dk/nrf5340/cpuapp 21.63s user 6.38s system 424% cpu 6.602 total |      |
|                    |                                                              |      |
|                    |                                                              |      |

