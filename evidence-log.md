# Evidence Log

| ID | File | What I did | What the image supports | What it does not prove |
|---|---|---|---|---|
| E01 | `01-server-front.jpeg` | Photographed the assembled server | R510 chassis, installed front carriers, two visibly empty positions | Disk health or RAID layout |
| E02 | `02-open-chassis.jpeg` | Removed the top cover and photographed the full interior | Internal layout, processors, memory banks, fan wall, adapters, fixed internal storage | Electrical health |
| E03 | `03-dual-power-supplies.jpeg` | Inspected the rear power modules | Two installed 750 W hot-swap supplies | Load sharing or PSU health |
| E04 | `04-front-drive-labels.jpeg` | Removed populated carriers and read disk labels | Four Dell-labeled Seagate SAS disks marked 146 GB and 15K RPM | SMART status or array membership |
| E05 | `05-internal-wd-red-drive.jpeg` | Inspected the stacked internal disks | WD Red WD10JFCX, 1 TB SATA; a second matching drive was also present | RAID level, contents, or health |
| E06 | `06-raid-battery.jpeg` | Located and read the RAID battery label | Dell FR463 lithium-ion battery, 3.7 V, 7 Wh | Remaining capacity or charge state |
| E07 | `07-raid-controller-and-cache.jpeg` | Inspected the RAID assembly and cache module | Controller hardware, cache module, SAS connections, and visible physical condition | A proven causal link to the POST error |
| E08 | `08-memory-module.jpeg` | Removed or exposed a DIMM label for identification | Samsung 4 GB registered DDR3 part number | Full memory health |
| E09 | `09-post-memory-warning.jpeg` | Powered the server and photographed POST | Two processors, 12 GB memory, CPU2 memory warning, H800 identification | Corrective action or long-term stability |
| E10 | `10-post-raid-error.jpeg` | Continued POST and recorded the failure screen | H800 firmware fault, no response, unrecoverable error, SDRAM connection warning | Exact failed component |
| E11 | `11-rear-io.jpeg` | Photographed the rear panel and connections | Rear I/O, network ports, management port, power connections, external controller ports | Network link or throughput |

All conclusions in the project should trace back to one or more evidence items or to a clearly labeled hypothesis.

