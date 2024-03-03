# Plugin to use with Pwnagotchi and the PiSugar2.

## This plugin DOES require using the official [pisugar-power-manager-rs](https://github.com/PiSugar/pisugar-power-manager-rs) install. 

# Install guide:
### Step 1, install PiSugar Manager
```bash
# Go to the home directory
cd ~

# Install PiSugar Power Manager 
curl http://cdn.pisugar.com/release/pisugar-power-manager.sh | sudo bash
```
## Download the support library

### Step 2
```bash
cd ~/
git clone https://github.com/PiSugar/pisugar2py.git
```
### Step 3
make sure to change /!CHANGE ME!/ to your pwnagotchi's python version see below for values
Jayofelony 64bit use `/python3.11/`
other is most likely `/python3.7/`
```bash
sudo cp -r ~/pisugar2py/ /usr/local/lib/!CHANGE ME!/dist-packages/pisugar2
```

# This installs the pisugar2 package into your python library
sudo ln -s ~/pisugar2py/ /usr/local/lib/python3.7/dist-packages/pisugar2

# Installs the user-plugin
sudo ln -s ~/pwnagotchi-pisugar2-plugin/pisugar2.py /usr/local/share/pwnagotchi/installed-plugins/pisugar2.py

In /etc/pwnagotchi/config.toml add:
```toml
main.plugins.pisugar2.enabled = true
main.plugins.pisugar2.shutdown = 5
main.plugins.pisugar2.sync_rtc_on_boot = true
```



PiSugar2 web settings are accessible at http://10.0.0.2:8421/#/

The support library exposes all of the available commands from the pi-sugar in a python library for developers
