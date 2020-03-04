Clone the OAI-5G repository twice, and name each **gNB** and **UE** respectively.

## Setup

### Common steps:
* `git clone https://gitlab.eurecom.fr/oai/openairinterface5g`
* `mv openairinterface5g/ gNB/` or `mv openairinterface5g/ UE/`
* `cd gNB/` or `cd UE/`
* `git checkout 915f11323ccd0f23a33865ae3f2d29192f7b137d`
* `source oaienv`
* `cd cmake_targets`
* `sudo ./buildoai -I`

### gNB specific:
* `sudo ./buildoai --gNB -w USRP`

### UE specific:
* `sudo ./buildoai --nrUE -w USRP`

## Running the Simulations
* `cd ran_build/build`
* [gNB] `gNB :sudo RFSIMULATOR=enb ./nr-softmodem -E -O ../../../targets/PROJECTS/GENERIC-LTE-EPC/CONF/gnb.band78.tm1.217PRB.usrpn300.conf --parallel-config PARALLELSINGLETHREAD --rfsim`
* [UE] `sudo RFSIMULATOR=127.0.0.1 ./nr-uesoftmodem --numerology 1 -r 217 -C 3510000000 --rfsim -d`
