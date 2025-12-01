Running a Podman Container as a Systemd Service

mkdir ~/.config/systemd/user -p – Create the systemd user directory.


cd ~/.config/systemd/user – Navigate into the systemd user directory.


podman run -itd --name testcontainer nginx – Start a container in detached mode.


podman generate systemd --name testcontainer --files --new – Generate systemd service files for the container.


systemctl --user daemon-reload – Reload systemd user daemon to detect new files of the service.


systemctl --user start container-testcontainer.service – Start the container as a systemd managed service.


systemctl --user enable container-testcontainer.service – Enable the service to auto-start on boot/login.







# We can use journalctl to view the container logs:




#Use Cases:

1. Managing small production workloads on VMs
2. Managing Home-lab setups
3. You want the container to start automatically after reboot
4. Full systemctl lifecycle management for containers
5. Integrated Logging and Auditing

