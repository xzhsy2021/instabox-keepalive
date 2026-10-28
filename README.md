# instabox-keepalive

Keeps the InstaBox free machine from being auto-paused (30 min idle on the free plan).

- `.github/workflows/keepalive.yml` — every 20 minutes, SSH into the machine and run `uptime`.
  SSH counts as activity, so the machine stays running; a paused machine is resumed by the same call.
- `.github/workflows/keepalive-touch.yml` — monthly commit, so GitHub never disables the schedule for 60 days of repo inactivity.
- A local Windows task (`InstaBoxKeepalive`, every 20 min) does the same from the desktop.

Secret: `IB_USER` — the SSH login user of the machine.

