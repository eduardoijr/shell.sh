#!/bin/bash


echo "       .__        _____       ";
echo "  ____ |__| _____/ ____\____  ";
echo "_/ __ \|  |/    \   __\/  _ \ ";
echo "\  ___/|  |   |  \  | (  <_> )";
echo " \___  >__|___|  /__|  \____/ ";
echo "     \/        \/             ";
#http://patorjk.com/software/taag/#p=display&c=echo&f=Graffiti&t=einfo
# by Eduardo 

echo ""
echo -e " \033[0;31m [!] TARGET  \033[0m  --> $1 "
ip=$(ping -4 -c 1 $1 | grep "64 bytes" | cut -d " " -f 5 | tr : " ")
echo ""
echo "----- IP DO ALVO $ip -----"
echo ""
echo -e " \033[0;32m [!] DESEJA FAZER UMA VARREDURA COMPLETA NESSE HOST?\033[0m --> (S/N)"
read host
clear
if [ $host = "S" -o $host = "s" ]
then
        sleep 2
        echo -e " \033[0;32m INICIANDO NMAP \033[0m --> $1  "
        echo ""
        sudo nmap -sS --open --top-ports=10 $1
        echo ""
        echo -e " \033[0;32m RESOLVENDO HOST \033[0m --> $1  "
        echo ""
        host $1
        sudo dnsenum --enum $1
        sudo theHarvester -d $1 -l 100 -b google
else
        clear
fi
