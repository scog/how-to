# How To: Check download speed using curl

---

### 50 Megabyte download

```bash
curl -s https://speed.cloudflare.com/__down?bytes=50000000 \
  -o /dev/null -w "Download Speed: %{speed_download} bytes/sec\n"
```

### 100 Megabyte download

```bash
curl -s https://speed.cloudflare.com/__down?bytes=100000000 \
  -o /dev/null -w "Download Speed: %{speed_download} bytes/sec\n"
```
