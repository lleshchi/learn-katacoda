# Start and enable Stratis

Now, start and enable the stratisd systemd service using the systemctl utility.

`systemctl start stratisd`{{execute}}

`systemctl enable stratisd`{{execute}}

You can check the stratisd version.

`stratis daemon version` {{execute}}

At any point, you may also check the status of stratisd.

`systemctl status stratisd`{{execute}}

If a stratisd service in an active state is listed, then stratisd is running.
