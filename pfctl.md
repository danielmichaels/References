# PfSense update issues

Recently I have been having weird errors when trying to update my PfSense box.

**Conditions:**

1. New update is released; local box on old version
2. GUI update pages says "Up to date" when it really isn't
3. BSD Shell `pkg update -f' returns errors such as: sqlite missing or can't route to pfsense.core etc

This is an issue with the VPN on the box. IPv6 is disabled and pfsense package updating needs to be
able to communicate over IPv6. 

## The Workaround

`pfctl -d` (pfctl --disable)

now run the command `pkg update -f` so it can rebuild its database and make the connections
to PfSense's backend.

Now check the GUI as this provides a visible way to check whether the connection is working, and
update the system as needed.

It will restart and automatically re-enable `pfctl`. For reference `pftctl -e` will re-enable the
packet filtering manually.
