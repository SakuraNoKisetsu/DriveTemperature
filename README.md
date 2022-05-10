
# Drive Temperature [![Badge License]][License] ![Badge Kernel]

*Linux Kernel Driver For Hard-drive Temperatures*

<br>

---

<div align = center>

[![Button Repository]][Repository]

</div>
	
---

<br>

## Features

- Reports the temperature of disk / solid state drives

- If supported, uses **ATC SCT Command Transport**

- Reads **SMART** attributes as fallback method.

<br>

#### ATC SCT

*If supported, tries to read out:*

- Historic Min / Max Temperature

- Temperature Limit

- Temperature
		
<br>
<br>

## Older Kernels

Building will require upstream commit `d188b0675b21`

> scsi: core: Add sysfs attributes for VPD pages 0h and 89h

*and possibly other **SCSI** core changes.*

<br>
<br>

## SysFS Entries

The `temp1_input` attribute is always present, <br>
others are only available if reported by the drive.

All temperatures are given in `Milli ℃`.

<br>

| Variable | Description
|:--------:|:-----------
| `temp1_input` | Current temperature

<br>

| Minimum | Maximum | Description
|:-------:|:-------:|:-----------
| `temp1_min` | `temp1_max` | Recommended continuous operating temperature
| `temp1_lowest` |  `temp1_highest` | Most extreme temperature of the current power cycle
| `temp1_lcrit` | `temp1_crit` | Temperature limit. <br><br> *Operating the device outside this temperature <br>limit may cause physical damage to the device.*

<br>
<br>

## References

- `ANS T13/1699-D Information technology - AT Attachment 8 - ATA/ATAPI Command Set (ATA8-ACS)`

- `ANS Project T10/BSR INCITS 513
Information technology - SCSI Primary Commands - 4 (SPC-4)`

- `ANS Project INCITS 557
Information technology - SCSI / ATA Translation - 5 (SAT-5)`

<br>


<!----------------------------------------------------------------------------->

[Button Repository]: https://img.shields.io/badge/The_Repository-37a779?style=for-the-badge

[Badge License]: https://img.shields.io/badge/License-GPL_2-blue.svg?style=for-the-badge
[Badge Kernel]: https://img.shields.io/badge/Linux_Kernel-5.5+-427819.svg?style=for-the-badge

[Repository]: https://github.com/groeck/drivetemp

[License]: LICENSE
