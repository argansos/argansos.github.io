---
layout:     post
title:      "INSTALLING CIRCOS ON MAC OSX"
subtitle:   "A step-by-setp setup instructions"
date:       2020-08-20 12:00:00
author:     "argansos"
header-img: "img/bg-tech.jpg"
catalog: true
tags:
    - tech
    - circos
    - macOS
---

##### 1. Install Homebrew

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

##### 2. Requirements before installing

```bash
perl -v
which make
```

> Be sure that Perl and make (Xcode) are installed

##### 3. Download and install Circos

```bash
sudo mkdir ~/Applications/circos/
sudo chown "$USER":admin ~/Applications/circos/
cd ~/Applications/circos/
curl -L http://circos.ca/distribution/circos-0.69-9.tgz -o circos-0.69-9.tgz
tar xvfz circos-0.69-9.tgz
rm circos-0.69-9.tgz
ln -s circos-0.69-9 current
export PATH=~/Applications/circos/current/bin/:$PATH
. ~/.zshrc
```

##### 4. Check for modules & instalation

```bash
~/Applications/circos/current/bin/circos -modules
```

> Remember the missing modules.

##### 5. Install missing Perl modules

Use CPAN to install and update modules

```bash
perl -MCPAN -e shell
```

> Be sure to answer yes to everything if this is your first time using CPAN

At cpan[1] consol, first update cpan:

```bash
install CPAN
```

Then, install the missing modules by using `install` command in cpan consol and exit the consol by run the command `exit`. E.g.

```bash
install Math::Bezier
exit
```

> IMPORTANT - if GD and/or GD::Polyline is missing, you must install libgd before installing GD

```bash
brew install libgd
brew install pkgconfig

perl -MCPAN -e shell # you may need root permission to install GD
install GD
install GD::Polyline
exit
```

##### 6. Update the shell configratuon

Now, you are ready for using circos. Be sure to add the path of circos into your environment by adding the following into .zshrc or .bashrc.

```bash
PATH="/Users/your_username/Applications/circos/current/bin${PATH:+:${PATH}}"; export PATH;
```

##### Reference
* [Aidan Quinn's post](http://aidanquinn.net/blog/blog/2015/11/11/installing-circos-on-mac-osx/)
* [Circos Official Documentation](http://circos.ca/software/installation/)
