PA-VM appliance

The VM-Series combines next-generation firewall security and advanced threat prevention to protect your virtualized environments from advanced cyberthreats. The VM-Series natively analyzes all traffic in a single pass to determine the application identity, the content within, and the user identity.

More informations on https://www.paloaltonetworks.com/products/secure-the-network/virtualized-next-generation-firewall/vm-series

HOW TO INSTALL
Download the appliance file: https://gns3.com/external/download?url=https%3A//raw.githubusercontent.com/GNS3/gns3-registry/master/appliances/pan-vm-fw.gns3a
Download the files for one of the supported version https://docs.gns3.com/appliances/pan-vm-fw.html#appliance_supported
Import the .gns3a file in GNS3 https://docs.gns3.com/1_3RdgLWgfk4ylRr99htYZrGMoFlJcmKAAaUAc8x9Ph8/index.html
APPLIANCE USAGE
Default Username: admin Default Password: admin PAN-VM goes through several iterations of host prompts during boot. This is normal and expected. Login is available when prompt is PA-VM login: Getting Started: To configure a static IP address at the console enter the following commands: configure set deviceconfig system ip-address netmask default-gateway type static set deviceconfig system dns-setting servers primary secondary commit

APPLIANCE REQUIREMENTS
RAM: 4096 MB

You need KVM enable on your machine or in the GNS3 VM.

APPLIANCE DOCUMENTATION
Documentation for using the appliance is available on https://www.paloaltonetworks.com/documentation/80/virtualization/virtualization

VERSION SUPPORTED

