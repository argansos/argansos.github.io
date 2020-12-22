---
layout:     post
title:      "MOUNT SYNOLOGY NFS SHARED FOLDER ON LINUX"
subtitle:   "A step-by-setp setup instructions"
date:       2020-12-16 10:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - linux
---

##### Mount directly via terminal (need to do it every time you restart the pc)

```bash
# Mount the nfs shared folder
sudo mount -t nfs 169.254.254.168:/volume1/tom /nfsfile
```
You may need to install nfs-common before you mount nfs shared folder.

##### Automatically mount after the computer started

```bash
# Edit the fstab file
sudo vi /etc/fstab
```

Then, append the following text in the end of the file, save and reboot.
> 169.254.254.166:/volume1/tom /nfsfile nfs defaults  0  0
