# Install
- https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository













<br><br>

---

<br><br>



# Troubleshooting

## Analyse

Ich habe die Docker-Desktop-Userlogs rekursiv nach Fehlern durchsucht:
```bash
grep -RinE '(error|fatal|panic|dashboard|electron)' ~/.docker/desktop/log | tail -n 200
```
Dadurch erschien u.a. die Zeile mit FATAL:setuid_sandbox_host.cc und dem Hinweis auf /opt/docker-desktop/chrome-sandbox.

### Minimaler Cheat Sheet: Wenn Docker Desktop (GUI) nicht startet
- Logs-Verzeichnis überfliegen:
```bash
ls -1 ~/.docker/desktop/log/host/
```
- Wichtigste GUI-/Electron-Fehler sehen:
```bash
tail -n 200 ~/.docker/desktop/log/host/"Docker Desktop.stderr.log"
```
- Alternativ schnell alle Fehler scannen:
```bash
grep -RinE '(error|fatal|panic|dashboard|electron)' ~/.docker/desktop/log | tail -n 200
```
- User-Service-Status + Journal prüfen:
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


### Ursache
- Das Dashboard (Electron) crasht sofort wegen falsch gesetzter Sandbox-Binary.
- In deinen Logs steht eindeutig:
```text
[...]/Docker Desktop.stderr.log: FATAL:setuid_sandbox_host.cc(158) The SUID sandbox helper binary was found, but is not configured correctly. Rather than run without sandboxing I'm aborting now. You need to make sure that /opt/docker-desktop/chrome-sandbox is owned by root and has mode 4755.
```
- Dein System läuft bereits auf X11 (KDE), also kein Wayland-Problem. Das Backend läuft, nur das GUI stirbt am `chrome-sandbox`.

### Fix (2 Befehle + Neustart des User-Services)
- Setze Owner und SUID-Bit korrekt:
```bash
sudo chown root:root /opt/docker-desktop/chrome-sandbox
sudo chmod 4755 /opt/docker-desktop/chrome-sandbox
```
- Optional prüfen:
```bash
ls -l /opt/docker-desktop/chrome-sandbox
# Erwartet: -rwsr-xr-x 1 root root ...
```
- User-Service neu starten:
```bash
systemctl --user restart docker-desktop
```
- Danach Dashboard starten (oder per Launcher):
```bash
/opt/docker-desktop/bin/docker-desktop >/dev/null 2>&1 &
```
