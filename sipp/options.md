### How to: options ping

This tutorial references the [`./etc/options-ping.xml`](./etc/options-ping.xml) template

1. Assign your variables:
```
myuser="someUser"         # username for the OPTIONS ping
remote_ip="10.10.0.50"    # IP of the remote SIP endpoint
sockets=2                 # max number of sockets to open
rate=0.5                  # pings per second
```

2. Run the command:
```
sipp -sf ./etc/options-ping.xml -m ${sockets} -r ${rate} -s ${myuser} ${remote_ip}
```
