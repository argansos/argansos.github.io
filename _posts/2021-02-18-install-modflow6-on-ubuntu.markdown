---
layout:     post
title:      "INSTALL MODFLOW6 ON UBUNTU"
subtitle:   "A step-by-setp setup instructions"
date:       2021-02-18 10:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - linux
    - modflow
---

##### Install the Fortran compiler gfortran

```bash
sudo apt-get install gfortran
```

##### Download the [latest version](https://www.usgs.gov/software/modflow-6-usgs-modular-hydrologic-model#hist) and unpack it
you may need to install p7zip-full to unpack the zip.

```bash
cd Downloads
mkdir MODFLOW
curl -OLC - https://water.usgs.gov/water-resources/software/MODFLOW-6/mf6.2.0.zip
7z x mf6.2.0.zip
```

##### Install the modflow6
```bash
cd make
make
```

After compiling we end up with the binary (mf6) and temporary object files in the subfolder .obj_temp and .mod_temp.

##### Test modflow6
```bash
cd ../examples/ex-gwt-henry-a
./../../make/mf6
```

p.s. I would recommend you to move <code style="color:red">mf6</code> to <code style="color:red">/opt</code>, better with also the examples, source code and documentations, and set appropriate folder and file permission, then create a link to it to call it directly.

##### Reference
* [Simon Wenkel's post](https://www.simonwenkel.com/2018/04/15/compiling-MODFLOW-on-linux.html)
