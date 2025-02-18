# Systemd

**Systemd** runs the script based on a timer unit that triggers a service at specified intervals.

- **Create Service (`notify.service`)** → Defines what to run
- **Create Timer (`notify.timer`)** → Defines when to run
- **Move to `~/.config/systemd/user/`** → So systemd finds them
- **Run `systemctl --user daemon-reload`** → Reload systemd
- **Run `systemctl --user enable --now notify.timer`** → Start & enable timer
- **Timer triggers service** → Runs script every 30 min

# Crontab

**Cron** runs the script at specified times by scheduling it in the crontab file.

- **Create Script (`notify.sh`)** → Defines what to run
- **Edit Crontab (`crontab -e`)** → Add a schedule
- **Add `*/30 * * * * /home/yakoti/notify.sh`** → Run script every 30 minutes
- **Cron triggers script** → Runs script at scheduled times

```crontab

crontab -e

*/30 * * * * /home/yakoti/notify.sh 2>/home/yakoti/folder for error logs
#every 30 min, every hour, every day, every month, every year.
```

```bash
crontab -l
#see the content
```


