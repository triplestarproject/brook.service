# brook.service

simple brook start service for systemd

you should change contents in <> for your information.

once done, copy the brook.service file into /etc/systemd/system

```bash
systemctl enable brook.service # run service for every reboot
systemctl reboot # reboot your server, and service will be running at next time
```

the example for brook.service:
```shell
[Unit]
Description=simple brook start service
After=network.target

[Service]
Type=simple
User=root
WorkingDirectory=/root/Downloads
ExecStart=/root/Downloads/brook server -l :2222 -p 123456 
Restart=always
RestartSec=1

[Install]
WantedBy=multi-user.target
```