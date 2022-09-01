﻿
## Migrate from Fortinet config into Azure Firewall Policy
author: [Jose Moreno](https://github.com/erjosito)

This script provides a way read an existing Fortinet Fortigate configuration and export commands into an existing Azure Firewall Policy. 

Example:

    python ./read_fortigate_config.py --file ./fortigate_output.txt --format json


*add the rules*
    az network firewall policy rule-collection-group collection rule add --name 1073742000 --source-addresses 10.15.5.20/32 10.15.5.40/32 10.15.5.30/32 10.15.5.50/32 10.5.22.140/32 10.5.22.145/32 10.5.22.150/32 10.5.22.155/32 --destination-addresses 10.10.40.21/32 10.10.40.22/32 --protocols tcp udp --destination-ports 288 33434

    az network firewall policy rule-collection-group collection rule add --name 1073742041 --source-addresses 10.15.5.40/32 10.15.5.50/32 10.5.22.140/32 10.5.22.150/32 --destination-addresses 10.10.40.21/32 10.10.40.22/32 --protocols tcp udp --destination-ports 22