# crypto-mining-linux
Setup of an Ubuntu 17.10 mining rig


Start scripts

There's 2 start scripts provided.
These need to be copied into /etc/systemd/system directory, as root. 

So copy the 2 files into 

/etc/systemd/system

These are the 2 start scripts:

ethminer.service
ethproxy.service

There's a dependency between ethminer and ethproxy, so ethminer will only start when ethproxy is available.

To load the start scripts, perform following steps (as root) :

systemctl daemon-reload
systemctl enable ethminer.service
systemctl enable ethproxy.service

Now you can verify they are enabled :
systemctl list-unit-files | grep eth

And they will start your ethminer and ethproxy on startup of the machine. To stop/start either, use :

systemctl start ethminer.service 

Logs are in the common journal, that you can tail using :
journalctl -xelf



