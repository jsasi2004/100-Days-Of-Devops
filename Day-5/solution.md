`ssh steve@stapp02`

`dnf install -y selinux-policy selinux-policy-targeted`

`nano /etc/selinux/config`

search for `SELINUX=` and make it `disabled`
