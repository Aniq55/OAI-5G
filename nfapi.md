nFAPI PNF---VNF

## Common Steps:
Clone the OAI in two separate folders: pnf_oai and vnf_oai:
* `git clone https://gitlab.eurecom.fr/oai/openairinterface5g.git`
* `git checkout a40f9d9d231710271cbc156bb06415dcee0a5fc9`

## PNF
### Config
* file: `targets/PROJECTS/GENERIC-LTE-EPC/CONF/oaiL1.nfapi.usrpb210.conf`
* no need to modify anything
### Build
* `source oaienv`
* `cd cmake_targets`
* `sudo ./build_oai --eNB -w USRP`
### Run
* `sudo -E ./lte_build_oai/build/lte-softmodem -O ../targets/PROJECTS/GENERIC-LTE-EPC/CONF/oaiL1.nfapi.usrpb210.conf`
(from cmake_targets)

## VNF
### Config
* file: `targets/PROJECTS/GENERIC-LTE-EPC/CONF/rcc.band7.tm1.50PRB.nfapi.conf`
Modify as per: `https://gitlab.eurecom.fr/oai/openairinterface5g/wikis/l2-nfapi-simulator/l2-nfapi-simulator-w-S1-same-machine`
### Build
* `source oaienv`
* `cd cmake_targets`
* `sudo ./build_oai --eNB -w USRP`
### Run
* `sudo -E ./lte_build_oai/build/lte-softmodem -O ../targets/PROJECTS/GENERIC-LTE-EPC/CONF/rcc.band7.tm1.50PRB.nfapi.conf `
(from cmake_targets)

