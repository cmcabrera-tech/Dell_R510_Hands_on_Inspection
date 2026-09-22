# Dell PowerEdge R510 Legacy Server Hardware Inspection & Component Documentation

![Status](https://img.shields.io/badge/status-inspection%20complete-brightgreen)
![Platform](https://img.shields.io/badge/platform-Dell%20PowerEdge%20R510-007DB8)
![Hardware](https://img.shields.io/badge/hardware-enterprise%20server-orange)
![RAID](https://img.shields.io/badge/RAID-PERC%20H700%20%7C%20H800-red)
![Diagnostics](https://img.shields.io/badge/diagnostics-POST%20%7C%20BIOS-blue)
![Documentation](https://img.shields.io/badge/documentation-evidence--based-informational)

> **Repository note:** The evidence photos came from the actual inspection. Any visible equipment identifiers were covered or obscured before publication. All images were reviewed before being included in this public repository.

---

## Project Overview

This repository documents a hands-on physical inspection of a legacy Dell PowerEdge R510 enterprise server.

The primary objective was to identify, inspect, and document the major hardware components that make up the system.

The inspection included:

- Opening the server chassis
- Identifying major internal and external components
- Temporarily removing selected components to inspect physical labels and specifications
- Documenting processors, memory, storage, RAID hardware, power, cooling, and network interfaces
- Inspecting visible cables and hardware connections
- Identifying loose, abnormal, or mechanically stressed components
- Capturing POST and BIOS information
- Documenting startup warnings and hardware faults

All components removed specifically for documentation were returned to their original positions after inspection.

A secondary objective was to perform a visual fault assessment based on physical observations and startup messages.

The server initially powered on but produced no video output. Limited troubleshooting was performed only to restore enough functionality to access and document POST and BIOS information.

The objective was **not** to fully repair or return the server to production service.

![Front view of the Dell PowerEdge R510](evidence/01-server-front.jpeg)

---

## Objectives

- Perform a physical inspection of a legacy Dell PowerEdge R510 server.
- Identify and document major server components.
- Record model numbers, part numbers, capacity, interface type, firmware, and other visible specifications where available.
- Temporarily remove selected removable components when required for documentation.
- Reinstall documented components in their original positions.
- Document the internal hardware layout.
- Inspect visible cable and hardware connections.
- Capture POST and BIOS information.
- Identify visible signs of damage, mechanical stress, loose connections, or abnormal component positioning.
- Record startup warnings and hardware faults.
- Distinguish confirmed observations from unverified diagnostic hypotheses.
- Create visual technical documentation of the server for portfolio and future reference.

---

## Inspection Workflow

1. Connected the server to power and attempted the initial startup.
2. Confirmed that the system powered on but produced no video output.
3. Disconnected power and opened the chassis for physical inspection.
4. Inspected the motherboard, processors, memory banks, storage devices, RAID hardware, cooling system, power supplies, expansion cards, and visible connections.
5. Confirmed that neither CPU1 nor CPU2 had memory installed.
6. Installed three compatible memory modules in the CPU1 memory bank to enable startup testing.
7. Inspected the RAID hardware.
8. Found a loose memory/cache module on the PERC H700 assembly located near the two internal 1 TB drives.
9. Carefully reseated the loose H700 memory/cache module.
10. Inspected the second RAID adapter and observed a memory/cache module that appeared visibly arched or mechanically stressed.
11. Intentionally left the mechanically stressed module untouched.
12. Temporarily removed selected components when necessary to document labels and specifications.
13. Reinstalled all components removed for documentation in their original positions.
14. Reconnected the server to power.
15. Confirmed that video output was restored.
16. Captured POST and BIOS information.
17. Attempted to identify a valid boot device for the operating system.
18. Documented hardware inventory, startup warnings, visual abnormalities, and confirmed faults.

---

## System Inventory

![Open chassis showing the internal parts](evidence/02-open-chassis-labeled.png)

| Area | Finding | Evidence Basis |
|---|---|---|
| Platform | Dell PowerEdge R510, 2U rack server | Chassis and BIOS |
| BIOS | Version 1.12.0 | Startup screen |
| Processors | 2 x Intel Xeon E5620 at 2.40 GHz | POST and BIOS |
| Memory | 3 x 4 GB ECC DDR3 modules, 12 GB total at 1067 MHz | Physical inspection, POST, and BIOS |
| Front Storage | 4 x Dell-labeled Seagate 146 GB 15K SAS hot-swap drives | Physical drive labels and front bays |
| Empty Front Bays | 2 visible carriers contained no drives | Physical inspection |
| Internal Storage | 2 x Western Digital Red WD10JFCX 1 TB SATA drives | Physical labels |
| RAID Controller 1 | Dell PERC H700 Integrated, DP/N `0R374M` | Physical controller label |
| RAID Controller 2 | Dell PERC H800, firmware package `12.10.2-0004` | POST |
| RAID Battery | Dell lithium-ion battery, type `FR463`, 3.7 V, 7 Wh | Physical label |
| Network | Integrated Broadcom 5716 dual-port Gigabit Ethernet | BIOS and rear I/O inspection |
| Power | 2 x Dell/Delta 750 W hot-swap power supplies | Physical labels |

The total label-reported raw disk capacity is approximately **2.584 TB decimal**.

This value represents raw installed disk capacity only and does not represent usable RAID capacity.

No RAID level, virtual disk configuration, filesystem state, operating system condition, or data integrity was verified.

---

## Inside the Chassis

After removing the top cover, I mapped the internal layout and identified the major assemblies.

The server contains:

- Two Intel Xeon processor sockets
- Separate memory banks for CPU1 and CPU2
- ECC DDR3 memory
- Front hot-swap SAS drive bays
- Two internally mounted SATA drives
- Dell PERC H700 Integrated RAID controller
- Dell PERC H800 RAID adapter
- RAID cache/memory modules
- RAID battery
- Fan wall
- Redundant hot-swap power supplies
- USB 3.0 expansion card
- Network interface card
- Integrated rear I/O interfaces
- System motherboard

Selected components were temporarily removed when necessary to read physical labels, part numbers, model information, interface types, capacities, and other identifying specifications.

All components removed for documentation were returned to their original positions.

The chassis showed moderate dust accumulation and normal physical wear consistent with legacy enterprise hardware.

No obvious burn damage or visibly swollen motherboard capacitors were observed during the limited inspection.

---

## Initial Power-On Condition

The server was initially connected to power and successfully powered on, but no video output was produced.

Because POST and BIOS information could not be documented without display output, the system was powered down and opened for physical inspection.

The troubleshooting performed at this stage was limited to restoring enough functionality to continue the documentation process.

It was not intended as a full repair.

---

## Memory Inspection and Installation

During the initial internal inspection, neither CPU1 nor CPU2 had memory installed in their respective memory banks.

To allow the server to proceed through startup testing, three compatible 4 GB ECC DDR3 memory modules were installed in the CPU1 memory bank.

This provided a total of **12 GB of installed memory**.

CPU2 remained installed without local memory.

After video output was restored, POST detected both processors and the installed memory but reported:

```text
Warning: Unsupported memory configuration detected.
CPU 2 installed with no memory.
```

The physical layout supports this message: three 4 GB Samsung registered DIMMs were installed in the CPU1 bank, while the CPU2 memory bank was empty. The server can detect the memory, but the topology does not follow the expected balanced configuration for two installed processors.

### RAID error

![POST screen showing the PERC H800 fault](evidence/10-post-raid-error.jpeg)

POST reported the following for the PERC H800:

```text
F/W is in Fault State
Adapter at Baseport is not responding
RAID Adapter Unrecoverable Error
Please check the SDRAM connection
```

POST also reported zero virtual drives on that adapter. This evidence confirms a controller-level startup fault. It does not, by itself, prove that the visibly arched module caused the fault.

## My fault assessment

| Priority | Finding | Why it matters | Confidence |
|---|---|---|---|
| High | PERC H800 enters a firmware fault state and reports an SDRAM connection error | The adapter cannot initialize normally and may block access to attached storage | Confirmed by POST |
| High | RAID cache or memory module appears arched or mechanically stressed | A poor connector contact or damaged module could be related to the SDRAM error | Physical observation, cause unconfirmed |
| Medium | CPU2 has no local memory | POST flags the configuration as unsupported and performance may suffer | Confirmed by POST and physical layout |
| Medium | No bootable device was detected | The server cannot start an operating system in its current verified state | Confirmed by POST |
| Medium | RAID battery condition is unknown | An aged or failed battery can disable write-back cache or generate controller warnings | Component confirmed, health untested |
| Unknown | Drive health and RAID membership | Labels identify the disks but do not establish SMART health, array state, or data integrity | Not tested |

The strongest current hypothesis is a problem in the H800 cache/SDRAM path, connector seating, or the adapter itself. The observed physical deformation makes that area worth checking first, but replacement should not begin until the controller, module, and connectors are safely inspected and tested.

## Recommended next diagnostic session

1. Disconnect power, follow ESD precautions, and photograph the controller and connectors before moving them.
2. Identify exactly which physical adapter corresponds to the H800 POST fault.
3. Inspect the cache module, socket, retaining clips, and battery cable for damage.
4. Reseat the cache module and controller only if the hardware shows no unsafe damage.
5. Boot again and record whether the SDRAM and firmware errors change.
6. Enter the PERC configuration utilities and export or photograph the physical-disk and virtual-disk state.
7. Balance memory across both processors using a configuration supported by the R510 manual.
8. Run Dell diagnostics and review the hardware event log.
9. Test the drives without initializing, clearing, or creating arrays until the value of any existing data is known.

## What this project demonstrates

- Safe physical access to rack-server hardware
- Component identification from labels, board markings, firmware screens, and connection paths
- Evidence-based separation of confirmed faults from hypotheses
- Storage and RAID awareness, including the risk of destructive configuration changes
- Clear technical documentation for a manager and for a future repair session

## Repository guide

| Path | Contents |
|---|---|
| [`evidence/`](evidence/) | Selected photographs from the inspection |
| [`notes/component-inventory.md`](notes/component-inventory.md) | Detailed component inventory |
| [`notes/fault-analysis.md`](notes/fault-analysis.md) | Reasoning behind the fault assessment |
| [`docs/Dell_PowerEdge_R510_Hands_On_Inspection_Report.pdf`](docs/Dell_PowerEdge_R510_Hands_On_Inspection_Report.pdf) | Formal inspection report |

## Scope limits

This was a visual and startup inspection. I did not verify drive health, RAID configuration, usable capacity, operating system status, data contents, battery health, network connectivity, or long-duration stability. The initial no-video condition cleared later, but I did not capture a confirmed corrective action, so I have not assigned a root cause.

## Portfolio Context

This project adds direct enterprise hardware inspection and legacy server fault assessment to a portfolio that also includes Windows administration, networking, Help Desk operations, PowerShell automation, endpoint management, and AI-assisted IT support.

Unlike the virtualized infrastructure projects in the portfolio, this project documents direct hands-on interaction with physical enterprise server hardware, including controlled component removal, identification, reinstallation, startup testing, BIOS/POST assessment, boot-device investigation, and evidence-based fault documentation.

## Author

**Carlos Cabrera**  
CompTIA A+ Certified | IT Support | Windows Administration | Networking | Hardware Troubleshooting
