## wifi learning notes

two types of scanning; active and passive scanning. Passive scanning is inefficient as it hops across all channels listening for beacons. Active scanning, on the other hand will still go through every channel but sends out a Probe Request management frame. The Probe Request asks what network is available on a given frequency (channel). 

Probe Requests are sent as a Broadcast Destination Address (ff:ff:ff:ff:ff:ff). Once this probe is sent the ProbeTimer countdown starts and waits for an answer. It will process any reply received within the ProbeTimer, if nothing is received the Station will move to the next channel and repeat this process.

Stations can send two types of Probe Requests; Directed Probe Requests and Wildcard or Null Probe Reqests. A Directed Probe Request will specify the SSID it is requesting. A Null Probe Request will set the SSID bit to 0 (meaning it is present, but empty). 

*Whats the difference between probes and beacons?*

A beacon is a management frame sent from an Access Point that details all of its important information. They are transmitted periodically to announce the presence of a WLAN. They are transmitted in a Infrastructure Basic Service Set (IBSS). IBSS beacon generation can be shared amongst stations.