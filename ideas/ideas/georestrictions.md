# Georestrictions

There are certain regions which are banned from communicating with other regions due to international sanctions or due to domestic restrictions. Since the platform is based in the United States, it must comply with these laws and the platform must be unavailable to investors from these regions.

A dynamic geo-restriction policy would detect the source ip of the requester, and ban them from accessing the page. One could also detect if the user is using a VPN or Tor and refuse to server users if regulations deem so.

A static geo-restriction policy would add ip blocks to iptables in order to refuse traffic from the banned clusters. This would be hard since there are tons of ip blocks belonging to these banned regions, and we would need to add a rule for each one of them.

