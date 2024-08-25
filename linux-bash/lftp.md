## How To: lftp commands

A few helpful `lftp` commands:

---

### Download with password prompt

```bash
# Assign your variables
username="<FTPUSER>"
download_file="/path/to/file.txt"
domain="ftps://some.ftp.site.io"

# Run the command
lftp -u ${username} -e "set ftp:ssl-force true; set ftp:ssl-protect-data true; get ${download_file}; exit;" ${domain}
```

### Download with no password prompt
```bash
# Assign your variables
username="<FTPUSER>"
password="<FTPPASS>"
download_file="/path/to/file.txt"
domain="ftps://some.ftp.site.io"

# Run the command
lftp -u "${username},${password}" -e "set ftp:ssl-force true; set ftp:ssl-protect-data true; get ${download_file}; exit;" ${domain}
```