---
layout:     post
title:      "CONNECT TO SERVER VIA SSH WITHOUT PASSWORD"
subtitle:   "A step-by-setp setup instructions"
date:       2021-01-15 10:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - linux
    - ssh
---

##### Generate ssh keygen

```bash
ssh-keygen -t rsa -b 4096 -C "example@email.com"
```

##### Copy the pub key to the server

```bash
ssh-copy-id account@server
```
