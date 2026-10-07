# Activity 1: Booting & systemd

A systemd service that prints "Hello" in ASCII art every time the VM boots.

## Files

- `hello_ascii.sh`: script that prints the ASCII art
- `hello_ascii.service`: systemd unit that runs the script at boot
- `Screenshot from 2026-10-07 19-34-43`: `journalctl` output showing the art

## Installation

```bash
sudo cp hello_ascii.sh /usr/local/bin/
sudo chmod +x /usr/local/bin/hello_ascii.sh
sudo cp hello_ascii.service /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable --now hello_ascii.service
```

## Verify

```bash
systemctl status hello_ascii.service
journalctl -b -u hello_ascii.service
```