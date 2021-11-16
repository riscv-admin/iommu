# IOMMU TG Charter

The I/O MMU Task Group develops a unified, advanced I/O MMU architecture suitable for Linux-class systems (as will be standardized by OS-A Platform specs), which includes the following capabilities:

- Address translation and access control of read/write requests by non-CPU agents (aka devices)
- Support for many concurrent access domains and devices - and associated translation context state
- Support for PCIe, including PRI, PASID, and ATS
- Virtualization support
  - Works effectively with CPU virtualization and AIA (i.e. the Hypervisor Extension and Advanced Interrupt Architecture)
  - PCIe MSI virtualization based on AIA
- Build upon the Priv 1.12 and Hypervisor extension MMU architectures (e.g. page tables), and other existing virtual memory extensions
  - Minimize differences between the CPU and IO MMU architectures
- Scalable from large-scale feature-rich systems down to smaller, simpler systems
- Support for loosely coupled, buffered interfaces to software (possibly via memory-based command/response/etc. buffers - tbd)
- Support for assigning physical memory types/attributes to device accesses
- Support for PMP-like functionality to protect M-mode resources from access by devices

The I/O MMU Task Group validates its specification for Embedded and Server use-cases using a testbed consisting of Linux and QEmu.
