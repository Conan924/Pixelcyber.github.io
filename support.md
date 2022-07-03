---
layout: page
title: Support
permalink: /support/
---

## FAQ for Thor

### 1、Sniff HTTP traffic on other device with Thor

[Sniffer Proxy FAQ >](../proxy-en/doc.md)

### 2. HTTPS decryption

#### Why need a "Thor SSL CA" certificate

HTTPS decryption need the "Thor SSL CA" installed and trusted by system to perform a MiTM for HTTPS traffics.

 A root certificate to perform a MiTM for decoding HTTPS traffics is an unique and standard common view and technology. 


"Thor SSL CA" certificate used in Thor for HTTPS decoding is safe and privacy security, it is generated randomly when Thor first launched and stored in app local keychain only.
Certificates between devices or users are different.

"Thor SSL CA" certificate is unnecessary, if you don't need HTTPS decryption.


#### Trust "Thor SSL CA" in iOS system

You need trust a CA manually after it was installed in `Profiles` since iOS10, as below


`Settings > General > About > Certificate Trust Settings`


#### Why need a VPN tunnel

Thor is a HTTP sniffer, a source of HTTP traffics will be necessary.

Thor used a VPN tunnel to set up a source of HTTP traffics from both Wi-Fi and cellular of local device.

All traffics sniffed by Thor stored in app local only, no records will be uploaded to remote server. (Even Thor doesn't have a remote server or something like that, it's totally a local sniffer tool.) 


### 3. Filter in Thor

**Session Filter**: filter you selected in homepage. It matches keywords or patterns in `Request Headers`.


**Packet Filter**: filter you selected in packets list. It matches keywords or patterns in `Request Headers`, `Response Headers` and `Response Body` data type.


**Export & Import**
* **f4thor**: file type for `Session Filter` and `Packet Filter`. You can export .f4thor files and share them to anyone or import .f4thor files from someone.

* **p4thor**: file type for Thor packet records. You can export packets as .p4thor files to backup or share to others who can import and analyze them in Thor.

* **har**: standard HTTP archive file is supported in Thor.

* **cURL**: Thor can export requests as curl commands.


## FAQ for Shu

### File Managing

#### File Grouping

"`Auto Group`" files by types into build-in Folders.

Entries:

* Swipe a file item > More > `Auto Group`

* Enter a folder > Edit > `Auto Group`


#### File extracting

* Compression file extract (password supported): zip, rar, 7z, tgz, tar, bz, tbz, gz, xz, txz, xar/xip, lz4, tlz, cpio, cpgz...

* Disk image: iso, udf, nrg, cab, wim, dmg, vhd, vmdk, qcow, uefif...
* File system: ntfs, fat, mbr, gpt, hfs, sfs
* Package: deb, rpm, crx, xpi, ar, PE file, ELF file, com file
* E-book, office documents, pdf, sketch
* Extract frames of tiff, icns, gif, apng, webp


#### File converting

* Export text file with different string encoding: GBK, UTF-8, UTF-16...
* Certificate format conversion (der, pem, p12, base64)
* ipynb/markdown -> html
* djvu -> jpg
* xml, json, plist, yaml convert to each other
* ps/eps -> pdf


### File Sharing

#### Mac/PC/Another Device <-> Shu

* iTunes File Sharing: better performance for huge files.
`Go to: Mac/PC > iTunes > Your iOS device > File Sharing > Apps > Shu`

* Wi-Fi File Sharing: convenient sharing between devices in the same LAN.

* Hotspot File Sharing: convenient sharing between devices in the same hotspot network.

* USB File Sharing: convenient sharing between iOS devices and macOS through USB cable.

* Files in Shu -> Sharing: Select files in Shu "File" > Add to "Shared Folder"

*Notice: Files in "Shared Folder" can be shared with iTunes.*


#### Shu <-> Other Apps

* Files in Other Apps -> Shu:
`Find export/share entry in other Apps > "Open in Shu" or "Copy to Shu"`

* Photos -> Shu:
`Select pictures in Photos > Open in Shu > then you can export all pictures as a zip file`

* "File" app -> Shu: drag files in "File" app to Shu directory.

* Shu -> Other Apps: Select files > export raw file/export as zip file > choose an app to share.

* Share with iTunes or Wi-Fi, if you want to export huge files.*

### HTTP downloading

* Detect download url in pasteboard automatically.

* Copy links in other apps > then launch Shu 

* Export links in other apps  > Open in Shu

* Custom request headers

*Notice: Audio/Video can not download.*


## Feedback

[Bugs report & suggestion](mailto:beta@pixelcyber.com): `beta@pixelcyber.com`