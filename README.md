Midlleware-TV


Install Midlleware for Ubuntu 18.04 LTS

1-Install Main Server

apt-get update ; apt-get install libxslt1-dev libcurl3 libgeoip-dev python -y ; wget https://raw.githubusercontent.com/rmartinsfer/middleware/main/settinngs.py ; sudo python install.py

2-Update Middleware

apt-get install unzip e2fsprogs python-paramiko -y && chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && rm -rf /home/xtreamcodes/iptv_xtream_codes/admin && rm -rf /home/xtreamcodes/iptv_xtream_codes/pytools && wget "https://streaming-servers.com/downloads/update.zip" -O /tmp/update.zip -o /dev/null && unzip /tmp/update.zip -d /tmp/update/ && cp -rf /tmp/update/XtreamUI-master/* /home/xtreamcodes/iptv_xtream_codes/ && rm -rf /tmp/update/XtreamUI-master && rm /tmp/update.zip && rm -rf /tmp/update && chattr +i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && /home/xtreamcodes/iptv_xtream_codes/start_services.sh

3-GeoLite2.mmdb Pernamently fix

cd /home/xtreamcodes/iptv_xtream_codes/crons/ && cp servers_checker.php servers_checker.php.orgi && rm servers_checker.php && wget https://streaming-servers.com/downloads/servers_checker.php && sudo chattr -i /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && sudo chmod 777 /home/xtreamcodes/iptv_xtream_codes/GeoLite2.mmdb && sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && sudo chmod 777 -R /home/xtreamcodes/iptv_xtream_codes/crons && sudo /home/xtreamcodes/iptv_xtream_codes/start_services.sh

4-Autostart on Server reboot

sudo nano /etc/crontab

@reboot root /home/xtreamcodes/iptv_xtream_codes/start_services.sh

5-PID Monitor Fix

wget "https://streaming-servers.com/downloads/pid_monitor.zip" -O /tmp/pid_monitor.zip -o /dev/null && unzip /tmp/pid_monitor.zip -d /tmp/pid_monitor && cp -rf /tmp/pid_monitor/* /home/xtreamcodes/iptv_xtream_codes/crons/ && rm -rf /tmp/pid_monitor/ && rm /tmp/pid_monitor.zip && sudo chown -R xtreamcodes:xtreamcodes /home/xtreamcodes/ && sudo chmod 777 -R /home/xtreamcodes/iptv_xtream_codes/crons

6-Login with User: admin and Psaaword: admin
