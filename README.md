packer-vib
===================

This repository contains content to build a vib file for ESXi. The goal is to configure a host to enable use as a target for the [Packer VMware builders](https://www.packer.io/docs/builders/vmware.html).

Specifically, it:
* Configures the firewall to allow VNC access
* Enables SSH and supresses the warning message
* Enables the GuestIPHack advanced option

Build Instructions
===================

`vibauthor -C -t stage -v packer.vib -O packer-offline-bundle.zip -f`

Resources
===================

https://www.virtuallyghetto.com/2012/09/creating-custom-vibs-for-esxi-50-51.html
https://www.virtuallyghetto.com/2015/05/a-docker-container-for-building-custom-esxi-vibs.html
https://nickcharlton.net/posts/using-packer-esxi-6.html
