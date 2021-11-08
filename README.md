# raspberrypi_fan

Move fancontrol.sh file to /etc/init.d, and make it executable:

```sh
sudo mv fancontrol.sh /etc/init.d/
sudo chmod +x /etc/init.d/fancontrol.sh
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
