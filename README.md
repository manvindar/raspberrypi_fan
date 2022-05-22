# raspberrypi_fan

Move fancontrol.sh file to /etc/init.d, and make it executable:

```sh
sudo mv fancontrol.py /usr/local/bin/fancontrol
sudo mv fancontrol.sh /etc/init.d/
sudo chmod +x /etc/init.d/fancontrol.sh
sudo chmod +x /usr/local/bin/fancontrol
```
Now we'll register the script to run on boot:
```sh
sudo update-rc.d fancontrol.sh defaults
```
Now, you can either restart your machine, or kick this off manually since it won't already be running:
```sh
sudo reboot
```
or
```sh
sudo /etc/init.d/fancontrol.sh start
````

And this is my systemd service file /usr/lib/systemd/system/usbreset.service which runs usb_reset.sh after my diplay manager has started:
```
[Unit]
Description=usbreset Service
After=gdm.service
Wants=gdm.service

[Service]
Type=oneshot
ExecStart=/path/to/usb_reset.sh
```
