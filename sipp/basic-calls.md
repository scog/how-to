### How to: generate basic sip calls with sipp

This tutorial references:
  - [`./etc/basic-call.xml`](./etc/basic-call.xml) sipp template as the call scenario
  - [`./etc/source-numbers.csv`](./etc/source-numbers.csv) as the source telephone numbers (sequential list)

---

1. Assign your environment variables:
```bash
scenario="./etc/basic-call.xml"       # sipp call scenario file
numbers="./etc/source-numbers.csv"    # source telephone number file
dest_number="2510091001"              # destination telephone number
dest_ip="10.10.0.5"                   # destination IP of the SIP endpoint
total_calls="20"                      # total number of calls
rate="0.5"                            # calls per second
max_connected="2"                     # maximum calls connected
```

2. Run the command:
```bash
sipp ${dest_ip}:5060 \
     -p 5060 \
     -sf ${scenario} \
     -inf ${numbers} \
     -s ${dest_number} \
     -m ${total_calls} \
     -r ${rate} \
     -l ${max_connected} 
```
