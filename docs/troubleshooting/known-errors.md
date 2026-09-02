# Known Error fixes

- Errors were encountered while processing: docker-ce
  E: Sub-process /usr/bin/dpkg returned an error code (1)
  - You can turn of your VPN. If this is not working try:

```bash
sudo systemctl restart systemd-networkd.service # (disconnected network)
sudo apt remove docker-ce # If you hadn't done so before
sudo apt install docker-ce # Should start docker.service
sudo systemctl status docker.service  # Verify docker.service is running
```
