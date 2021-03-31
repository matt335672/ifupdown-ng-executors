# ifupdown-ng-executors

Additional executors for ifupdown-ng as used in Alpine Linux

## macvlan
### Description
Use to create a macvlan interface. Useful if you want to use the poor man's bridge provided as part of a Linux NIC to commmunicate between kvm guests and the host

### Example
```
auto meth0
iface meth0 inet dhcp
        use macvlan
        requires eth0
        hostname myhost
        #imode bridge
```

## ipv6-nolocal
### Description
Remove the IPv6 link local address on an interface if it's not required
at all (e.g. for a host interface that's not needed on teh host when
VT-d is not available).

### Example
```
iface wan0
        link-type dummy
        use ipv6-nolocal
        mtu 1508
```
