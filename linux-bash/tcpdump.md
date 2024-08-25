## How To: tcpdump commands

A few tricks with `tcpdump`

---


### Capture traffic for an entire subnet of `10.10.10.X`
```bash
tcpdump -i <interface> -nqt -s0 'net 10.10.10' -w file.pcap

# And port 53 (DNS)
tcpdump -i <interface> -nqt -s0 'net 10.10.10 and port 53' -w file.pcap
```

### Capture traffic from a remote machine via SSH and send directly to Wireshark
```bash
#
# Note: you must have sudo ability on the remote machine (or permission to run tcpdump as a normal user)
#
#
### LINUX ###
# Note: you must have sudo ability on the remove machine
ssh 10.10.0.1 "sudo tcpdump -s0 -U 'port 80' -w -" | wireshark -k -i -

#
### MAC OSX ###
# Set the path for Wireshark
wireshak="/Applications/Wireshark.app/Contents/MacOS/Wireshark"

# Run the command
${wireshark} -k -i <( ssh 10.10.0.1 sudo tcpdump -s0 -U 'port 80' -i ens18 -w - )
```

