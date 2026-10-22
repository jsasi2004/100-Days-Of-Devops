`sudo dnf install -y cronie`

`sudo systemctl enable --now crond`

`sudo crontab -e`

paste `*/5 * * * * echo hello > /tmp/cron_text` press `esc` then `:wq+enter`