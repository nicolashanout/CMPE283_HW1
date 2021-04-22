# CMPE_HW1

## Team Members
Nicolas Hanout 012303434
Heng Jerry Quan 014560130

## Contributions
- Nicolas Hanout
Implemented detail reporting for VM Entry and VM Exit controls.
- Heng Jerry Quan
Implemented detail reporting for Procbased and Procbased2 controls.

## Steps
<ol>
  <li> Define MSR value constants in CMPE283-1.c for procbased, procbased2, entry, and exit controls
  <li> For each MSR value, find corresponding control bits and names in SDM and add to struct
  <li> In detect_VMX_features(), add rdmsr() and prinfo() to read and print info from MSR, report capabilities
  <li> Call make from terminal to compile new module
  <li> Insert new module into kernel with `sudo insmod cmpe283-1.ko`
  <li> Check output of module using `sudo dmesg` (sudo may or may not be needed)
</ol>
