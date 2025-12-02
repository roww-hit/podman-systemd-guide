# Running a Podman Container as a Systemd Service

## Quick Start (All Steps)
You can run the following commands to set up the directory, start the container, and convert it to a systemd service.

```bash
# 1. Create the systemd user directory and navigate into it
mkdir -p ~/.config/systemd/user
cd ~/.config/systemd/user

# 2. Start a container (Example: Nginx)
podman run -itd --name testcontainer nginx

# 3. Generate systemd service files for the container
podman generate systemd --name testcontainer --files --new

# 4. Reload systemd to detect the new service files
systemctl --user daemon-reload

# 5. Start the container as a systemd managed service
systemctl --user start container-testcontainer.service

# 6. Enable the service to auto-start on boot/login
systemctl --user enable container-testcontainer.service

##View Logs
To check the container logs using journalctl:
journalctl --user -u container-testcontainer.service
