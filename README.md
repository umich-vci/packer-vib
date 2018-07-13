packer-vib
===================

This repository contains content to build a vib file for ESXi. The goal is to configure a host to enable use as a target for the [Packer VMware builders](https://www.packer.io/docs/builders/vmware.html).

Specifically, it:
* Configures the firewall to allow VNC access
* Enables SSH and supresses the warning message
* Enables the GuestIPHack advanced option

This has been tested with ESXi 6.0 Update 3, ESXi 6.5 Update 2, and ESXi 6.7.
It is possible it would work with ESXi 5.5.

If using this with ESXi 6.5 or 6.7, VNC password support seems to have been
removed. You must set `vnc_disable_password` to `true` in your Packer template.

Install Instructions
===================
    $ esxcli software acceptance set --level=CommunitySupported
    $ esxcli software vib install -v http://github.com/umich-vci/packer-vib/releases/download/v1.0.0-1/packer.vib

Build Instructions
===================

`vibauthor -C -t stage -v packer.vib -O packer-offline-bundle.zip -f`

Resources
===================

https://www.virtuallyghetto.com/2012/09/creating-custom-vibs-for-esxi-50-51.html
https://www.virtuallyghetto.com/2015/05/a-docker-container-for-building-custom-esxi-vibs.html
https://nickcharlton.net/posts/using-packer-esxi-6.html
