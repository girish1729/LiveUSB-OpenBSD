
# LiveUSB OpenBSD - A bootable OpenBSD for your pendrive[amd64]

![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/puffy72.png)

## What is LiveUSB OpenBSD?

It is quite easy to a create a bootable USB stick/pendrive/flash with OpenBSD. 

I wanted to create one and realized that this will be of general
use.

A USB memory stick that you can carry with you on a keychain. 

You can use that to get back into your favorite OpenBSD ecosystem
without touching the hard disk of the laptop on which it runs. 

Kindly note that this release only works on __64 bit Intel and AMD based
architectures. For the new Mac series and other RISC based systems this
won't work__.

These LiveUSB images are based on 
[OpenBSD version 7.2 made on Oct 20,2022](https://www.openbsd.org/72.html).

Kindly note that this is a volunteer effort; hence strictly `unofficial`.

You need a minimum of two writable media for getting this going. 

One is your host medium which runs your current OS like 

- Linux 
- Mac 
- Windows. 

Then you need a USB flash or pendrive on which you plan to install OpenBSD.

**IT WILL WIPE EVERYTHING IN USB STICK BEWARE!!!** :bomb:

Also remember that these images ignore the size of the USB medium. 

The images you have here, all 3 flavors write to a 64 GB medium.

Why? These days the USB pendrives found in market are of that capacity.

You can find a much better [page at Sourceforge](https://liveusb-openbsd.sourceforge.io)

## Instructions for using this OS image


> The OS images on this website till Oct 27, 2022 were broken as they are
> not using GPT.
> 
> Those of you that downloaded already and found the USB pendrive not
> booting kindly try out the new GPT images. These should work.
> 
> If your hardware is too old and uses BIOS instead of GPT then please
> [get in touch](mailto:girish@spamcheetah.com) and we will get it
> booting.


Using the OS images in this project needs a fairly decent level of
familiarity with the Linux or Mac command line. 

You can get this going from Windows as well. 

Just the method is different.

There are instructions for flashing this from Linux, Mac as well as
Windows [here](https://liveusb-openbsd.sourceforge.io/docs/installation-instructions).

## Downloads table

---


|OpenBSD LiveUSB variant | Download size | Download link|
| ------------ | ---------- | --------- |
|[LiveUSB Minimal image without X](/liveusb-minimal) | 600M|[:link:](https://sf.net/projects/liveusb-openbsd/files/LiveUSB-Minimal.img.zst/download)
|[LiveUSB XFCE](/liveusb-xfce)| 1.4G| [:link:](https://sf.net/projects/liveusb-openbsd/files/LiveUSB-XFCE.img.zst/download)
|[LiveUSB Gnome](/liveusb-gnome)| 2.0G|[:link:](https://sf.net/projects/liveusb-openbsd/files/LiveUSB-Gnome.img.zst/download)

---

### Make your choice, download, [and enjoy!](https://liveusb-openbsd.sourceforge.io/docs/installation-instructins)


## The size and checksums of image files

Please verify the SHA256 checksums from the table below.


---



| Download file | Download image size |  [SHA256 Checksum](https://en.wikipedia.org/wiki/SHA_hash_functions) of ZIPPED image
| ------------ | ---------- | -------- |
|LiveUSB-Minimal.img |628867626 Bytes|7a43aa5aacf111537a3a9ed17932ff975378d6544866b618d334f01bd2506894|
|LiveUSB-XFCE.img |1506529382 Bytes |a3ee15cb1f625f90eba0d4cd4dcf2e72a35963def72ca0a5c23e0026b33a1b54|
|LiveUSB-Gnome.img |2229280782 Bytes |5f4e2e27196c72bfdebf4f8dfffe59b6ee0ad9595f8bcc338ab482ebfd9c8544|

---

> Unzipped image size is always 59768832000 bytes. 
> This is to fit into a 64GB target medium.

There is a trick to look at progress whilst checking checksum for
large files.


```shell
    $ pv LiveUSB-Minimal.img.zst | sha256sum
```


```shell
    $ unzstd LiveUSB-Minimal.img.zst
```

To learn about `zstd compression` check 
[this project](https://www.github.com/facebook/zstd)

In all the 3 variants you can always add and remove packages.

Use 

- [pkg\_add(1)](https://man.openbsd.org/pkg_add)
- [pkg\_delete(1)](https://man.openbsd.org/pkg_delete)

commands in case my choices do not agree with yours.

One of the key attractions for me in OpenBSD is the ports system.

```shell
   root# cd /usr
   root# ftp https://cdn.openbsd.org/pub/OpenBSD/7.2/ports.tar.gz
   root# pv ports.tar.gz|tar zxpf - 
   root# cd /usr/ports/net/softflowd
   root# make install clean
```

You can do a lot of really excellent things with ports.
Completely upto you.

If you wish to have LiveCD/LiveDVD instead, please refer to our other
[LiveCD OpenBSD project](http://livecd-openbsd.sf.net) project.

### The root and user passwords for all 3 variants

You can login as 
   - user `live` 
   - password `live123`

The root password is `foo1729`

Don't blame me for this. It is only a hobby project.

The rock solid stability and performance is a thing to experience.

## Screenshots from XFCE variant

![LiveUSB OpenBSD XFCE](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/xfce/xfce.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/xfce/xfce2.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/xfce/xfce3.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/xfce/xfce4.webp)

## Screenshots from Gnome variant

![LiveUSB OpenBSD Gnome](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/gnome/gnome1.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/gnome/gdm.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/gnome/gnome2.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/gnome/gnome3.webp)

## Screenshots from Minimal variant

![LiveUSB OpenBSD Minimal](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/minimal/min-shot1.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/minimal/min-shot2.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/minimal/min-shot3.webp)
![LiveUSB OpenBSD](https://raw.githubusercontent.com/girish1729/LiveUSB-OpenBSD/main/images/minimal/min-shot4.webp)



### Enjoy the power of [OpenBSD](https://www.openbsd.org)

Please do not forget to thank the devs for an amazing project.

