F5 BIG-IP LTM VE appliance

The BIG-IP family of products offers the application intelligence that network managers need to ensure applications are fast, secure, and available. All BIG-IP products share a common underlying architecture, F5's Traffic Management Operating System (TMOS), which provides unified intelligence, flexibility, and programmability. Together, BIG-IP's powerful platforms, advanced modules, and centralized management system make up the most comprehensive set of application delivery tools in the industry. BIG-IP Virtual Edition (VE) is a version of the BIG-IP system that runs as a virtual machine in specifically-supported hypervisors. BIG-IP VE emulates a hardware-based BIG-IP system running a VE-compatible version of BIG-IP software.

More informations on https://f5.com/products/modules/local-traffic-manager

HOW TO INSTALL
Download the appliance file:https://gns3.com/external/download?url=https%3A//raw.githubusercontent.com/GNS3/gns3-registry/master/appliances/f5-bigip.gns3a
Download the files for one of the supported version https://docs.gns3.com/appliances/f5-bigip.html#appliance_supported
Import the .gns3a file in GNS3.https://docs.gns3.com/1_3RdgLWgfk4ylRr99htYZrGMoFlJcmKAAaUAc8x9Ph8/index.html


APPLIANCE USAGE
Console credentials: root/default. WebUI credentials: admin/admin. The boot process might take a few minutes without providing any output to the console. Please be patient (or set console to vnc to see tty outputs). In case the 'localhost emerg logger: Re-starting chmand' log appears on the console, you can find the solution here: https://devcentral.f5.com/questions/big-ip-ltm-ve-on-kvm

APPLIANCE REQUIREMENTS
RAM: 4096 MB

You need KVM enable on your machine or in the GNS3 VM.

APPLIANCE DOCUMENTATION
Documentation for using the appliance is available on https://support.f5.com/kb/en-us/products/big-ip_ltm/manuals/product/bigip-ve-kvm-setup-11-3-0.html


