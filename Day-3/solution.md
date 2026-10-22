`ssh tony@stapp01`

`sudo nano /etc/ssh/sshd_config`

search for permitrootlogin and make it no and restart sshd service

`sudo systemctl restart sshd`