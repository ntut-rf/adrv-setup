# Install prerequisites

1. Install requied system packages

  ```console
  # apt-get install build-essential libncurses-dev device-tree-compiler
  ```
  
2. Install Xilinx Vivado HLx Editions

  * Download from https://www.xilinx.com/support/download.html
  * Install to `/opt/Xilinx/`

# Build firmware

1. Init repository
  ```console
  $ git clone https://github.com/seanstone/plutosdr-fw
  $ cd plutosdr-fw
  $ git submodule init
  $ git submodule update
  ```

2. Build for ADRV9364
  ```console
  $ make TARGET=adrv9364
  ```
