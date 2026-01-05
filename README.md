# latency

Deploying this role may not get everything configured immediately.  Beyond the normal latency in updating world-wide DNS, there are also some scripts deployed by this role that will run eventually, but not immediately.

The external IP address of the home network is reported periodically (if a host on the home network is configured with the `dns-internal` role), so that information may not be immediately available after deployment.

The IP address of this host is mapped to the various names and aliases of this host and the domain by a dhclient hook script.  It will be run the next time DHCP updates, and that information will not be immediately available after deployment.  At time of writing, the DHCP lease time on the VPS used for this role seems to be about 15 minutes.

Some of this may be unavoidable, but some could definitely be improved.
