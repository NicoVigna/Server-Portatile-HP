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
