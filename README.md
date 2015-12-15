# VirtualBox Network Benchmarks

This repository contains iperf3 benchmarks that were taken from inside a VirtualBox guest, which was connecting over Host-Only networking (Windows 8 host). The guests used were Windows 10 (64-bit) and Ubuntu 14.04 (32-bit).

- Intel PRO/1000 MT Desktop (82540EM);
- Intel PRO/1000 MT Server (82545EM);
- Paravirtualized network adapter (virtio-net).

*Note: The Intel PRO/1000 T Server (82543GC) device was not tested as I was having trouble getting it to work reliably.*

## Results

|             |   82540EM     |    82545EM   |   virtio-net  |
|:-----------:|:-------------:|:------------:|:-------------:|
| Linux - TCP | 36.1464 Mbps  | 18.8011 Mbps | 1,320.69 Mbps |
| Linux - UDP | 406.820 Mbps  | 406.603 Mbps | 2,083.84 Mbps |
| Win10 - TCP | 1,899.58 Mbps | 1,880.43 Mbps | 423.516 Mbps |
| Win10 - UDP | 990.990 Mbps  | 461.042 Mbps | 1,007.62 Mbps|
