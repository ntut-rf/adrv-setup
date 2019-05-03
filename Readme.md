* Environment: Ubuntu 18.04

# ADRV9364

### Build firmware

See [Build_firmware.md](Build_firmware.md)

### Hardware setup

1. Insert SD card
2. Connect Power, USB, Ethernet 
3. Switch on power

### Login via serial port

1. Connect USB-UART such that the red LED is on.
2. Login via serial terminal. For example,
  ```console
  $ picocom -b 115200 /dev/ttyUSB0
  ```
  account/password: `root`/`analog`

### Network initial configuration

The IP address for the host and the device need to be set. For example,

```console
(adrv9364) # fw_setenv ipaddr_eth 192.168.1.1
(adrv9364) # fw_setenv ipaddr_host 192.168.1.100
(adrv9364) # reboot
```

You can adjust the IP address configuration for different devices.

### Login via network

Once the network is configured, you can login via ssh:

```console
$ ssh root@192.168.1.1
```
password: `analog`

# GNURadio

### Installation

1. Install GNURadio

```console
# apt-get install gnuradio
```

2.  Install GNURadio blocks for IIO

```console
# apt-get install libiio-dev libad9361-dev gr-iio
```
### Usage

`(no module specified)` -> `Industrial IO` -> `PlutoSDR Source/Sink`

* __Device URI__: `192.168.1.1`
* __RF Bandwidth(MHz)__: Configures TX/RX analog filters
* __Sample Rate(MSPS)__: Frequency at which the hardware will input/output samples

For more information, see https://wiki.analog.com/resources/tools-software/linux-software/gnuradio

Example RX flowgraph: [rx.grc](rx.grc)
