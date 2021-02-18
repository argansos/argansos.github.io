---
layout:     post
title:      "SET THE PRIORITY OF NETWORK CONNECTION IN UBUNTU"
subtitle:   "A step-by-setp setup instructions"
date:       2020-12-15 20:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - linux
    - network
---

##### script

```bash
# Install the ifmetric
sudo apt-get install ifmetric

# List the metric of interface
route -n
```

> Kernel IP routing table<br />
> Destination     Gateway         Genmask         Flags Metric Ref    Use Iface<br />
> 0.0.0.0         10.42.0.1       0.0.0.0         UG    100    0        0 eth0<br />
> 0.0.0.0         10.42.0.2       0.0.0.0         UG    600    0        0 wlan0

```bash
# Set preferred interface with lower metric
sudo ifmetric wlan0 50

# List the metric of interface
route -n
```

> Kernel IP routing table<br />
> Destination     Gateway         Genmask         Flags Metric Ref    Use Iface<br />
> 0.0.0.0         10.42.0.2       0.0.0.0         UG    50     0        0 wlan0<br />
> 0.0.0.0         10.42.0.1       0.0.0.0         UG    100    0        0 eth0


##### Reference
* [StackExchange](https://superuser.com/questions/331720/how-do-i-set-the-priority-of-network-connections-in-ubuntu)
