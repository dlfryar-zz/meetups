
sudo apt-get update; sudo apt-get dist-upgrade -y

sudo apt-get install ipmitool openssh-server tree most build-essential git -y

# Install KVM
sudo apt-get install qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils virt-manager -y

git clone https://git.openstack.org/openstack-dev/devstack


DESCRIPTION
       This program lets you manage Intelligent Platform Management Interface (IPMI)  functions  of  either
       the  local  system,  via  a kernel device driver, or a remote system, using IPMI v1.5 and IPMI v2.0.
       These functions include printing FRU information, LAN configuration,  sensor  readings,  and  remote
       chassis power control.

       IPMI management of a local system interface requires a compatible IPMI kernel driver to be installed
       and configured.  On Linux this driver is called OpenIPMI and it is included  in  standard  distribu‐
       tions.   On Solaris this driver is called BMC and is included in Solaris 10.  Management of a remote
       station requires the IPMI-over-LAN interface to be enabled and configured.  Depending on the partic‐
       ular  requirements of each system it may be possible to enable the LAN interface using ipmitool over
       the system interface.

# Disable "Password Policy Check Enable" to use simple passwords for the demo


ipmitool lan print 1

ipmitool user set name 2 admin
ipmitool user set password 2
ipmitool user enable 2
ipmitool user priv 2 4 1
ipmitool channel setaccess 1 2 ipmi=on
ipmitool channel setaccess 1 2 link=on


NAME
       dmidecode - DMI table decoder

DESCRIPTION
       dmidecode  is  a tool for dumping a computer's DMI (some say SMBIOS) table contents in a human-read‐
       able format. This table contains a description of the system's hardware components, as well as other
       useful pieces of information such as serial numbers and BIOS revision. Thanks to this table, you can
       retrieve this information without having to probe for the actual hardware.  While  this  is  a  good
       point  in  terms  of  report  speed and safeness, this also makes the presented information possibly
       unreliable.

       The DMI table doesn't only describe what the system is currently made of, it  also  can  report  the
       possible evolutions (such as the fastest supported CPU or the maximal amount of memory supported).

       SMBIOS  stands  for  System Management BIOS, while DMI stands for Desktop Management Interface. Both
       standards are tightly related and developed by the DMTF (Desktop Management Task Force).

       As you run it, dmidecode will try to locate the DMI table. If it succeeds, it will then  parse  this
       table and display a list of records like this one:

sudo dmidecode -t 0
