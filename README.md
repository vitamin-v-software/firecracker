This repository contains a ported version of Firecracker for RISC-V. It enables lightweight virtual machine creation and management.

Firecracker is used alongside FunctionBench and Kata Containers in WP4 in UC3: Serverless Cloud. 
For setting up the UC3 demonstrator follow the guide [here](https://github.com/vitamin-v-software/functionbench/tree/master/Kata_Firecracker_FB) 

This repository contains a modified version of :contentReference[oaicite:0]{index=0} with experimental **RISC-V** support.

## Summary of Changes

- Added RISC-V–specific modules with conditional compilation to avoid impacting `x86_64` and `aarch64`.
- Implemented interrupt delivery using `KVM_IRQ_LINE` instead of `IRQFD`, due to RISC-V limitations.
- Extended `IrqTrigger` for VirtIO devices and introduced `IrqLineTrigger` for the serial console.
- Stored the raw VM file descriptor to issue interrupt-related `ioctl` calls.

## Supported Devices

- VirtIO block  
- VirtIO net  
- Serial console  

## Status

- Successfully boots RISC-V microVMs on QEMU hosts with AIA support.
