xmrMiner-tk1 - A CUDA based miner for Monero

This project is forked from [KlausT's](https://github.com/KlausT/ccminer-cryptonight) ccminer version.
ccminer is developed by Christian Buchner's &amp; Christian H.'s and modified by tsiv for Cryptonight mining.
This project is forked from [psychocrypt](https://github.com/xmrMiner/xmrMiner) xmrMiner version. 
It modifed to work on the Nvidia Jetson TK1 and was done only for educational purposes 

# Performance Overview

gpu | launch param | xmrMiner [hash/s] | KlausT ccminer [hash/s] | speedup [%] | clock [MHz] | watt
:---|:------------:|:------------------|:------------------------|:------------|:------------|----
Nvidia Tegra TK1 | 12x16 | 15 |  |  |756-951 MHz |8 W | 


# Requirements

## Hardware

xmrMiner-tk1 supports only NVIDIA Jetson TK1 with CUDA 6.5 (32bit) Ubuntu 16.04 Linux ARMv7 
I have the latest flash build from October 2017 Linux tegra-ubuntu 3.10.40 

https://developer.nvidia.com/linux-tegra-rel-21
Tegra_Linux_Sample-Root-Filesystem_R21.6.0_armhf.tar


## Software
- NVIDIA [CUDA](https://developer.nvidia.com/cuda-downloads) =6.5
  - Ubuntu: Download CUDA for Jetson TK1 accordingly to the Nvidia documentation or use some already made scrtipts 
            https://gist.github.com/jetsonhacks/6da905e0675dcb5cba6f 
- host compiler
  - gcc >=4.6 (depends on your current CUDA version)
  - clang >=3.9 (support compile of the host and device code)
- SSL support
  - Ubuntu: sudo apt-get install libssl-dev
- CMake >=3.3.0
  - Ubuntu: I have used pkgsrc current; bootstrap and build cmake, you can find your repo with proper cmake
- Curl
  - Ubuntu: sudo apt-get install libcurl4-gnutls-dev
- Jansson
  - Ubuntu: Download sources from https://github.com/akheron/jansson compile and install  
- git
  - Ubuntu: sudo apt-get install git

# Install

1. create and enter the project folder:
  - mkdir -p xmrMiner-tk1
  - cd xmrMiner-tk1
2. download the xmrMiner-tk1 source code
  - git clone ....
4. configure xmrMiner (search for all dependencies) 
  - cmake -DCUDA_ARCH=32 . 
5. compile
  - make -j 
6. start xmrMiner
  - `./xmrMiner`
  - `./xmrMiner --help`

