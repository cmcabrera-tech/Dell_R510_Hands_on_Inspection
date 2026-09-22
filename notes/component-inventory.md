# Component Inventory

This inventory records what I could confirm during the physical inspection and startup capture.

| Category | Component | Quantity | Identification | Verification |
|---|---|---:|---|---|
| Chassis | Dell PowerEdge R510 | 1 | 2U rack server, approximately 2011 | Chassis and BIOS |
| CPU | Intel Xeon E5620 | 2 | 2.40 GHz, 4 cores each | POST and BIOS |
| Memory | Samsung ECC registered DDR3 | 3 DIMMs | M393B5273CH0-YH9, 4 GB each, PC3L-10600R | Physical label |
| Front disks | Dell-labeled Seagate Cheetah 15K.7 | 4 | SAS, 146 GB, 15K RPM, firmware EH02 | Removed-drive labels |
| Empty front carriers | No disk installed | 2 | Visible empty carriers | Physical inspection |
| Internal disks | WD Red WD10JFCX | 2 | SATA, 1 TB each, NASware 2.0 | Physical labels |
| Internal RAID | Dell PERC H700 Integrated | 1 |  | Controller label |
| External RAID | Dell PERC H800 | 1 | Firmware package 12.10.2-0004 | POST |
| RAID battery | Dell rechargeable lithium-ion battery | 1 | Type FR463, 3.7 V, 7 Wh | Physical label |
| Network | Broadcom 5716 dual-port Gigabit Ethernet | 1 integrated controller | NIC1 and NIC2 enabled | BIOS |
| USB expansion | Add-in USB card | 1 | Black card with blue USB ports | Physical inspection |
| Power supply | Dell/Delta D750P-S0 | 2 | 750 W, 80 Plus Platinum | Physical labels |
| Cooling | Delta FFC0612DE fan modules | Approximately 5 visible | 12 V, 1.68 A, Dell | Physical labels and inspection |
| Motherboard | Dell system board | 1 | | Physical label |
| Management | iDRAC6 | 1 | Firmware 1.70.21, configuration utility 1.61 | POST |
| Backplane | Primary backplane | 1 | Firmware 1.10 | POST |

## Capacity statement

- Front raw capacity: 4 x 146 GB = 584 GB
- Internal raw capacity: 2 x 1 TB = 2 TB
- Total label-reported raw capacity: 2.584 TB decimal

No usable-capacity estimate is possible until the RAID levels, virtual disks, disk membership, and disk health are verified.

