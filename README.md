# check_disk_space
Check disk space on your linux server and push a webhook notification on teams channel

As simple as dowload, configure webhook url and threesold. 

Script limits the analysis to "/dev" mounting points. Feel free to change it in this line

#Obtener el espacio libre en disco de todos los discos que empiezan por /dev
DISK_USAGE=$(df -h | awk '/^\/dev/ { sub("%", "", $(NF-1)); if ($NF != "/") print $NF " " $(NF-1); else print "root " $(NF-1); }')
