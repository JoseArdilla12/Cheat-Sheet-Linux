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

#Enable Block:<br>
````
0 13 * * * sudo sqlite3 /etc/pihole/gravity.db "update 'adlist' set 'enabled'=0 where id='13';" ; /usr/local/bin/pihole restartdns reload-lists >/dev/null
````

#Disable Block:<br>
````
0 15 * * * sudo sqlite3 /etc/pihole/gravity.db "update 'adlist' set 'enabled'=1 where id='13';" ; /usr/local/bin/pihole restartdns reload-lists >/dev/null
````

