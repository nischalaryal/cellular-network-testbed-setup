# LTE Testbed SETUP Using OpenAirInterface and Magma Core
Some line...

## UE SETUP
Following devices and softwares were used for setting up a Commercially Off-The Shelf (COTS) User equipment.
- Hardware
  - Samsung Galaxy S4
  - Gemalto SIM card reader
  - Sysmocom Programmable SIM card
- Software
  - [pySim](https://github.com/osmocom/pysim)
  
 ### Steps
 1. Install [pySim](https://github.com/osmocom/pysim) and all it's dependencies. This repo also has a [documentation](https://osmocom.org/projects/pysim/wiki) regarding all the functionalities that can be achieved from the program. After downlading the program, access the folder. 
 
 **Note:** At the time of writing, executing the following code was sufficient. In future, you might need to adjust it according to the updates made in the program.
 
```
sudo apt install pcscd pcsc-tools libccid libpcsclite-dev python-pyscard
```
```
git clone git://git.osmocom.org/pysim.git 
```
``` 
cd pysim
```

2. To program the simcard, add the card into the card reader and attach it to the system. To verify if the card is recognized by the system or not, use the following command.
```
pcsc_scan
```
If the card reader is identified, the output of the command could be something like this.
```
TODO: Add the result
```

3. Next, we need following information to program into the sim card. 
**Note:** All values used here does not necessarily match your requirement. Especially ADM key.

| Variable | Description | Value Used |
| --- | --- | --- |
| `ADM` | Administrative key for SIM card. Provided during purchase. VERY IMPORTANT. | 2611488 |
| `MCC` | Mobile Country Code | 208 |
| `MNC` | Mobile Network Code | 93 |
| `Name` | Name of SIM card shown on the phone. | Magic |
| `IMSI` | International Mobile Subscriber Identity | 208930000000008 |
| `Ki` | Authentication Key | 8baf473f2f8fd09487cccbd7097c6862 |
| `OPC` | Operator Authentication Key | 2117cd3f66beb0811e6c72bc9ba82b3a |

**Note: The MCC and MNC values need to exactly match in the eNodeB configuration file and the core network. Ki and OPC values need to match exactly with the values stored in core network for successful attachment of UE.**

4. Once all the values are ready, we program the SIM card using pysim.
```
TODO: Add code
```

5. Finally, we setup APN value which will be used for setting up internet access. Go to your mobile data option in settings. Search for Access Point Names (APN) option and add a new apn setting with ```Name``` as ```oai``` and ```APN``` value ```oai.ipv4```. The name can be according to your choice as long as it matches with the value stored in core network.

## OAI RAN SETUP
Ran setup

## OAI Core Netowrk Setup
oai ran

## Magma Core Network Setup
magma core
