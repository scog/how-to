## How to: openssl commands

A few helpful commands for `openssl`

---

### Check certificate chain
```bash
# Assign your domain variable
domain="scog.in"

# Run the command
echo | openssl s_client -connect twitter.com:443 2>/dev/null
```

### Check certificate expiry
```bash
# Assign your domain variable
domain="scog.in"

# Run the command
echo | openssl s_client -connect ${domain}:443 2>/dev/null | openssl x509 -noout -dates
```
