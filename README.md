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

1. Define MSR value constants in CMPE283-1.c for procbased, procbased2, entry, and exit controls
2. For each MSR value, find corresponding control bits and names in SDM and add to struct
3. In detect_VMX_features(), add rdmsr() and prinfo() to read and print info from MSR, report capabilities
4. Call make from terminal to compile new module
5. Insert new module into kernel with `sudo insmod cmpe283-1.ko`
6. Check output of module using `sudo dmesg` (sudo may or may not be needed)

<pre>
[ 1104.110866] CMPE 283 Assignment 1 Module Start
[ 1104.110868] Pinbased Controls MSR: 0x7f00000016
[ 1104.110869]   External Interrupt Exiting: Can set=Yes, Can clear=Yes
[ 1104.110870]   NMI Exiting: Can set=Yes, Can clear=Yes
[ 1104.110871]   Virtual NMIs: Can set=Yes, Can clear=Yes
[ 1104.110872]   Activate VMX Preemption Timer: Can set=Yes, Can clear=Yes
[ 1104.110873]   Process Posted Interrupts: Can set=No, Can clear=Yes
[ 1104.110874] Exit Controls MSR: 0x7fffff00036dff
[ 1104.110875]   Save debug controls: Can set=Yes, Can clear=No
[ 1104.110876]   Host address-space size: Can set=Yes, Can clear=Yes
[ 1104.110877]   Load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[ 1104.110878]   Acknowledge interrupt on exit: Can set=Yes, Can clear=Yes
[ 1104.110879]   Save IA32_PAT: Can set=Yes, Can clear=Yes
[ 1104.110880]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[ 1104.110880]   Save IA32_EFER: Can set=Yes, Can clear=Yes
[ 1104.110881]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[ 1104.110882]   Save VMX-preemption timer value: Can set=Yes, Can clear=Yes
[ 1104.110883]   Clear IA32_BNDCFGS: Can set=No, Can clear=Yes
[ 1104.110884]   Conceal VMX from PT: Can set=No, Can clear=Yes
[ 1104.110885]   Clear IA32_RTIT_CTL: Can set=No, Can clear=Yes
[ 1104.110886]   Load CET state: Can set=No, Can clear=Yes
[ 1104.110887]   Load PKRS: Can set=No, Can clear=Yes
[ 1104.110887] Entry Controls MSR: 0xffff000011ff
[ 1104.110888]   Load debug controls: Can set=Yes, Can clear=No
[ 1104.110889]   IA-32e mode guest: Can set=Yes, Can clear=Yes
[ 1104.110890]   Entry to SMM: Can set=Yes, Can clear=Yes
[ 1104.110891]   Deactivate dual-monitor treatment: Can set=Yes, Can clear=Yes
[ 1104.110892]   load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[ 1104.110893]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[ 1104.110894]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[ 1104.110895]   Load IA32_BNDCFGS: Can set=No, Can clear=Yes
[ 1104.110896]   Conceal VMX from PT: Can set=No, Can clear=Yes
[ 1104.110896]   Load IA32_RTIT_CTL: Can set=No, Can clear=Yes
[ 1104.110897]   Load CET state: Can set=No, Can clear=Yes
[ 1104.110898]   Load PKRS: Can set=No, Can clear=Yes
[ 1104.110899]   Save debug controls: Can set=Yes, Can clear=No
[ 1104.110900]   Host address-space size: Can set=Yes, Can clear=Yes
[ 1104.110901] Procbased Controls MSR: 0xfff9fffe0401e172
[ 1104.110902]   Interrupt-window exiting: Can set=Yes, Can clear=Yes
[ 1104.110903]   Use TSC offsetting: Can set=Yes, Can clear=Yes
[ 1104.110904]   HLT exiting: Can set=Yes, Can clear=Yes
[ 1104.110905]   INVLPG exiting: Can set=Yes, Can clear=Yes
[ 1104.110905]   MWAIT exiting: Can set=Yes, Can clear=Yes
[ 1104.110906]   RDPMC exiting: Can set=Yes, Can clear=Yes
[ 1104.110907]   RDTSC exiting: Can set=Yes, Can clear=Yes
[ 1104.110908]   CR3-load exiting: Can set=Yes, Can clear=No
[ 1104.110909]   CR3-store exiting: Can set=Yes, Can clear=No
[ 1104.110910]   CR8-load exiting: Can set=Yes, Can clear=Yes
[ 1104.110911]   CR8-store exiting: Can set=Yes, Can clear=Yes
[ 1104.110912]   Use TPR shadow: Can set=Yes, Can clear=Yes
[ 1104.110913]   NMI-window exiting: Can set=Yes, Can clear=Yes
[ 1104.110913]   MOV-DR exiting: Can set=Yes, Can clear=Yes
[ 1104.110914]   Unconditional I/O exiting: Can set=Yes, Can clear=Yes
[ 1104.110915]   Use I/O bitmaps: Can set=Yes, Can clear=Yes
[ 1104.110916]   Monitor trap flag: Can set=Yes, Can clear=Yes
[ 1104.110917]   Use MSR bitmaps: Can set=Yes, Can clear=Yes
[ 1104.110918]   MONITOR exiting: Can set=Yes, Can clear=Yes
[ 1104.110919]   PAUSE exiting: Can set=Yes, Can clear=Yes
[ 1104.110920]   Activate secondary controls: Can set=Yes, Can clear=Yes
[ 1104.110921] Procbased Controls 2 MSR: 0x8ff00000000
[ 1104.110921]   Virtualize APIC accesses: Can set=Yes, Can clear=Yes
[ 1104.110922]   Enable EPT: Can set=Yes, Can clear=Yes
[ 1104.110923]   Descriptor-table exiting: Can set=Yes, Can clear=Yes
[ 1104.110924]   Enable RDTSCP: Can set=Yes, Can clear=Yes
[ 1104.110925]   Virtualize x2APIC mode: Can set=Yes, Can clear=Yes
[ 1104.110926]   Enable VPID: Can set=Yes, Can clear=Yes
[ 1104.110927]   WBINVD exiting: Can set=Yes, Can clear=Yes
[ 1104.110928]   Unrestricted guest: Can set=Yes, Can clear=Yes
[ 1104.110929]   APIC-register virtualization: Can set=No, Can clear=Yes
[ 1104.110930]   Virtual-interrupt delivery: Can set=No, Can clear=Yes
[ 1104.110930]   PAUSE-loop exiting: Can set=No, Can clear=Yes
[ 1104.110931]   RDRAND exiting: Can set=Yes, Can clear=Yes
[ 1104.110932]   Enable INVPCID: Can set=No, Can clear=Yes
[ 1104.110933]   Enable VM functions: Can set=No, Can clear=Yes
[ 1104.110934]   VMCS shadowing: Can set=No, Can clear=Yes
[ 1104.110935]   Enable ENCLS exiting: Can set=No, Can clear=Yes
[ 1104.110936]   RDSEED exiting: Can set=No, Can clear=Yes
[ 1104.110937]   Enable PML: Can set=No, Can clear=Yes
[ 1104.110937]   EPT-violation #VE: Can set=No, Can clear=Yes
[ 1104.110938]   Conceal VMC non-root operation from Intel PT: Can set=No, Can clear=Yes
[ 1104.110939]   Enable XSAVES/XRSTORS: Can set=No, Can clear=Yes
[ 1104.110940]   Mode-based execute control for EPT: Can set=No, Can clear=Yes
[ 1104.110941]   Use TSC scaling: Can set=No, Can clear=Yes
</ pre>
