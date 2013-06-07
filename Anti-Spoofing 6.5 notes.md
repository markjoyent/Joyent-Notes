Joyent-Notes
============

Anti-Spoofing 6.5 notes


for i in `dladm show-vnic | grep net | awk '{print $1}'` ; do p sdc-zone-net-attr 5873c20e-5647-488c-9c32-714750972ca7 $i allow_ip_spoofing 1 ; done

Command to check (after you shutdown / boot the VM) that ip spoofing has indeed been disabled:



dladm show-linkprop -p protection -z <UUID> net0



**if it's successfully turned off, the "ip-nospoof" will be gone from the left column**

