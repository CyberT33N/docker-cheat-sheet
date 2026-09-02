# Install
- https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository









<br><br>

---

<br><br>



# Troubleshooting

## Analysis

I recursively searched the Docker Desktop user logs for errors:
```bash
grep -RinE '(error|fatal|panic|dashboard|electron)' ~/.docker/desktop/log | tail -n 200
```
Among others, this surfaced the line with FATAL:setuid_sandbox_host.cc and the hint at /opt/docker-desktop/chrome-sandbox.

### Minimal cheat sheet: When Docker Desktop (GUI) does not start
- Scan the logs directory:
```bash
ls -1 ~/.docker/desktop/log/host/
```
- See the most important GUI/Electron errors:
```bash
tail -n 200 ~/.docker/desktop/log/host/"Docker Desktop.stderr.log"
```
- Alternatively, quickly scan all errors:
```bash
grep -RinE '(error|fatal|panic|dashboard|electron)' ~/.docker/desktop/log | tail -n 200
```
- Check user service status + journal:
```bash
systemctl --user status docker-desktop | sed -n '1,120p'
journalctl --user -u docker-desktop -b -n 200
```





<br><br>

---

<br><br>


## FAQ



### docker-desktop not starting

#### Linux:


### Cause
- The dashboard (Electron) crashes immediately because of an incorrectly set sandbox binary.
- Your logs state clearly:
```text
[...]/Docker Desktop.stderr.log: FATAL:setuid_sandbox_host.cc(158) The SUID sandbox helper binary was found, but is not configured correctly. Rather than run without sandboxing I'm aborting now. You need to make sure that /opt/docker-desktop/chrome-sandbox is owned by root and has mode 4755.
```
- Your system is already running on X11 (KDE), so this is not a Wayland problem. The backend runs; only the GUI dies at `chrome-sandbox`.

### Fix (2 commands + restart of the user service)
- Set owner and SUID bit correctly:
```bash
sudo chown root:root /opt/docker-desktop/chrome-sandbox
sudo chmod 4755 /opt/docker-desktop/chrome-sandbox
```
- Optionally verify:
```bash
ls -l /opt/docker-desktop/chrome-sandbox
# Expected: -rwsr-xr-x 1 root root ...
```
- Restart the user service:
```bash
systemctl --user restart docker-desktop
```
- Then start the dashboard (or via launcher):
```bash
/opt/docker-desktop/bin/docker-desktop >/dev/null 2>&1 &
```
