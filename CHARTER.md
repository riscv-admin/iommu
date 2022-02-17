# IOMMU TG Charter

The I/O MMU Task Group will develop a unified, advanced IOMMU architecture appropriate for RISC-V platforms and operating systems that support the virtual memory systems and the two-stage address translations defined by the privileged specification. The IOMMU complements the RISC-V MMU capabilities defined by the privileged specification to provide similar address translation and protection functions for accesses from I/O devices.

The IOMMU functionality is applicable in systems that need to efficiently support I/O virtualization when hosting guest operating systems on top of type-1 and type-2 hypervisors but also non-virtualized systems to isolate DMA-capable devices and to protect from malicious devices and software driver bugs. Moreover, on such systems the IOMMU enables performance optimizations and allows user-level processes to directly control I/O devices and program them with virtual addresses while the IOMMU can perform address translation and protection in hardware; examples of such I/O devices are DMA-capable NICs, GPUs, etc.

The IOMMU architecture specification will be a *Non-ISA* specification and will support the following capabilities:
- Address translation and access control of read/write requests by non-CPU agents and devices
- Support multiple concurrent access domains and devices - and their associated translation contexts
- Support standard interfaces such as PCIe (including ATS, PASID, and PRI) and typical on-chip interconnects and buses
- Virtualization:
  - Works effectively with CPU virtualization and AIA (i.e. the Hypervisor Extension and Advanced Interrupt Architecture)
  - PCIe MSI virtualization based on AIA
- Build upon the Priv 1.12 and Hypervisor extension MMU architectures (e.g. page tables), and other existing virtual memory extensions, as well as allowing for support of future virtual memory extensions similarly to the hart MMU architecture
  - Minimize differences between the CPU and IOMMU architectures
- Define loosely-coupled interfaces to software such as memory-based queues and buffers for commands, responses, errors etc. and other MMIO control
- Optional hardware performance monitoring unit
- Optional hardware support for IOMMU virtualization
- Assigning physical memory types/attributes to accesses from devices and the IOMMU
- Ensure that the IOMMU functionality can co-exist with physical memory protection mechanisms that might exist in the system to isolate M-mode resources from access by devices and the IOMMU itself

The I/O MMU Task Group will validate its specification using a testbed with Linux and QEMU for embedded and server/datacenter use-cases.

