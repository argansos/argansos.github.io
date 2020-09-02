---
layout:     post
title:      "INSTALLING RSYNC WITH SPECIFIC VERSION ON MAC OSX"
subtitle:   "A step-by-setp setup instructions"
date:       2020-09-02 20:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - rsync
---

##### script

```bash
# Compile rsync 3.0.6

# Download and unarchive rsync and its patches
cd ~/Download
curl -L -O http://rsync.samba.org/ftp/rsync/src/rsync-3.0.6.tar.gz
tar -xzvf rsync-3.0.6.tar.gz
rm rsync-3.0.6.tar.gz
curl -L -O http://rsync.samba.org/ftp/rsync/src/rsync-patches-3.0.6.tar.gz
tar -xzvf rsync-patches-3.0.6.tar.gz
rm rsync-patches-3.0.6.tar.gz
cd rsync-3.0.6

# Apply patches relevant to preserving Mac OS X metadata
patch -p1 <patches/fileflags.diff
patch -p1 <patches/crtimes.diff
patch -p1 <patches/hfs-compression.diff

# Configure, make, install
./prepare-source
./configure
make
sudo make install

# Verify your installation
/usr/local/bin/rsync --version
```

##### Reference
* [Fred Valentin's github](https://gist.github.com/Sounds-of-Science/7561838)
