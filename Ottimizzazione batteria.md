<!-- ho deciso di installare TLP -->

sudo apt update && sudo apt install tlp

<!-- devo modificare il file di conf -->

sudo nano /etc/tlp.conf

<!-- modifiche da inserire nel file conf -->

START_CHARGE_THRESH_BAT0=50
STOP_CHARGE_THRESH_BAT0=60

<!-- applicazione regole -->

sudo tlp start
sudo systemctl enable tlp

<!-- purtroppo non funziona -->

user@host:~$ sudo tlp-stat -b
--- TLP 1.8.0 --------------------------------------------

+++ Battery Care
Plugin: generic
Supported features: none available

+++ Battery Status: BATC
/sys/class/power_supply/BATC/manufacturer = Intel SR 1
/sys/class/power_supply/BATC/model_name = SR Real Battery
/sys/class/power_supply/BATC/cycle_count = 0 (or not supported)
/sys/class/power_supply/BATC/charge_full_design = 4230 [mAh]
/sys/class/power_supply/BATC/charge_full = 3271 [mAh]
/sys/class/power_supply/BATC/charge_now = 3271 [mAh]
/sys/class/power_supply/BATC/current_now = 0 [mA]
/sys/class/power_supply/BATC/status = Full

/sys/class/power_supply/BATC/charge_control_start_threshold = (not available)
/sys/class/power_supply/BATC/charge_control_end_threshold = (not available)
/sys/class/power_supply/BATC/charge_behaviour = (not available)

Charge = 100.0 [%]
Capacity = 77.3 [%]
