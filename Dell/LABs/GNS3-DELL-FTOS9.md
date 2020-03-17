Dell OS9 appliance

Dell Networking OS9 (formerly FTOS).
OS9 powers the Dell Networking product portfolio and has been hardened in some of the largest and most demanding environments in the world to meet stringent reliability, scalability and serviceability requirements.

Download and uncompress zip files from the Dell support site - corresponding to the FTOS/OS9 image name. Please 'Select FTOS for S-Series OS-EMULATOR'. Import the resulting ISO image.

More informations on http://www.dell.com/us/business/p/open-platform-software/pd

HOW TO INSTALL
Download the appliance file: https://gns3.com/external/download?url=https%3A//raw.githubusercontent.com/GNS3/gns3-registry/master/appliances/dell-ftos.gns3a
Download the files for one of the supported version https://docs.gns3.com/appliances/dell-ftos.html#appliance_supported
Import the .gns3a file in GNS3 https://docs.gns3.com/1_3RdgLWgfk4ylRr99htYZrGMoFlJcmKAAaUAc8x9Ph8/index.html
APPLIANCE USAGE
Make sure the Boot priority of the configuration template is HDD or CD. Abort the BCM process and format the flash after first boot by entering these commands: en format flash: Sometimes the flash device is not available after boot.

APPLIANCE REQUIREMENTS
RAM: 512 MB

You need KVM enable on your machine or in the GNS3 VM.

VERSION SUPPORTED

