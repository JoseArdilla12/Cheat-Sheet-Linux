# Cheat Sheet Pihole

Agregar y quitar dominios por command line<br>
````
pihole --white-wild -l
pihole --white-wild facebook.com tiktok.com
pihole --white-wild -d facebook.com tiktok.com

pihole -w -h
pihole -w facebook.com
pihole -b facebook.com
````

## Activar/Desactivar Adlists en Crontab

#Disable Block:<br>
````
0 13 * * * /etc/pihole/redsocial-almuerzo.sh

#!/bin/sh

/usr/bin/sqlite3 /etc/pihole/gravity.db "update 'adlist' set 'enabled'=0 where id='13'; update 'adlist' set 'enabled'=0 where id='14'" ; /usr/local/bin/pihole restartdns reload-lists >/dev/null
````

#Enable Block:<br>
````
0 15 * * * /etc/pihole/redsocial-block.sh

#!/bin/sh

/usr/bin/sqlite3 /etc/pihole/gravity.db "update 'adlist' set 'enabled'=1 where id='13'; update 'adlist' set 'enabled'=1 where id='14'" ; /usr/local/bin/pihole restartdns reload-lists >/dev/null
````


