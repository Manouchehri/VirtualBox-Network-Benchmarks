# VirtualBox Network Benchmarks

This repository contains iperf3 benchmarks that were taken from inside a VirtualBox guest, which was connecting over host-only networking. 

- Intel PRO/1000 MT Desktop (82540EM);
- Intel PRO/1000 MT Server (82545EM);
- Paravirtualized network adapter (virtio-net).

*Note: The Intel PRO/1000 T Server (82543GC) device was not tested as I was having trouble getting it to work reliably.*

## Results

|             |    82540EM    |     82545EM   |   virtio-net  |
|:-----------:|:-------------:|:-------------:|:-------------:|
| Linux - TCP | 36.1464 Mbps  | 18.8011 Mbps  | 1,320.69 Mbps |
| Linux - UDP | 406.820 Mbps  | 406.603 Mbps  | 2,083.84 Mbps |
| Win10 - TCP | 1,899.58 Mbps | 1,880.43 Mbps | 423.516 Mbps  |
| Win10 - UDP | 990.990 Mbps  | 461.042 Mbps  | 1,007.62 Mbps |

The slow throughput on the Intel cards inside Linux are likely due to a multi-core bug. Disabling extra cores may "fix" it, but that's not an acceptable solution in most situations.

## Host system details

The host system had the following specs:

- Oracle VirtualBox 4.3.30 r101610
- [Intel® Core™ i5-4570S Processor at 2.9 GHz (Quad)](http://ark.intel.com/products/75044/Intel-Core-i5-4570S-Processor-6M-Cache-up-to-3_60-GHz)
- 8 GB of RAM

## Guest details

### Linux

The Linux guest was running Ubuntu 14.04 (32-bit).

### Windows

The Windows guest was running Windows 10 (64-bit).
