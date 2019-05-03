* Environment: Ubuntu 18.04

# Installation

### Install GNURadio

```console
# apt-get install gnuradio
```

### Install GNURadio blocks for IIO

```console
# apt-get install libiio-dev libad9361-dev gr-iio
```

# ADRV9364

1. Insert SD card
2. Connect Power, USB, Ethernet 
3. Switch on power

### Login via serial port

1. Connect USB-UART such that the red LED is on.
2. Login via serial terminal. For example,
  ```
  $ picocom -b 115200 /dev/ttyUSB0
  ```
  account/password: `root`/`analog`


# GNURadio

`(no module specified)` -> `Industrial IO` -> `PlutoSDR Source/Sink`

Device URI: `192.168.4.1`
