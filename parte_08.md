<< [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 9](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_09.md) >>
<br><br>

## Cron

1. Crie uma pasta em algum local para armazenar o script, criei na raiz uma pasta chamada script

   `mkdir scripts`
<br><br>  
2. Em seguida crie um arquivo chamado monitoring.sh dentro da pasta criada

   `cd scripts`
   `touch monitoring.sh`
<br><br>   
3. Altere o arquivo monitoring.sh para printar na tela as informações solicitadas pelo subject

   | Informação  |     Onde encontrar      |  
   |:---------|:--------------|
   | #Architecture | através do comando uname -a |
   | #CPU physical | esta info está dentro do arquivo /proc/cpuinfo na linha physical.id |
   | #vCPU | esta info está dentro do arquivo /proc/cpuinfo na linha processor |
   | #Memory Usage | através do comando free -m |
   | #Disk Usage | através do comando tf -h ?????? |
   | #CPU load | através do comando top -b -n1, buscando a linha que contém o Cpu |
   | #Last boot | através do comando who -b |
   | #LVM use | Com o comando lsblk é possível ver as unidades type lvm. Podemos fazer uma condicional caso encontre o lvm e printar yes |
   | #Connexions TCP | ??? |
   | #User log | através do comando who, é possível saber os usuários logados. Podemos fazer um script para contar quantos usuários |
   | #Network |:--------------|
   | #Sudo |:--------------|
   
   
  Para testar o script enquanto o desenvolve basta, executá-lo via bash
  
   `bash scripts/monitoring.sh`
<br><br> 
4. Acesse as configurações do Cron

   `crontab -e`
<br><br>    
5. Acrescente uma regra para que um script seja executado a cada 10 minutos

   `*/10 * * * * sh /path/to/script`
 <br><br>   
   


echo -ne "ARCHITECTURE: "; uname -a
echo -ne "CPU PHYSICAL: "; grep -c processor /proc/cpuinfo
echo -ne "VIRTUAL CPU: "; cat /proc/cpuinfo | grep processor | wc -l
echo -ne "MEMORY USAGE: "; free -m | awk 'NR==2{printf "%s/%sMB (%.2f%%)\n", $3,$2,$3*100/$2}'
echo -ne "DISK USAGE: "; df -h | awk '$NF=="/"{printf "%d/%dGB (%s)\n", $3,$2,$5}'
echo -ne "CPU LOAD: "; top -bn1 | grep load | awk '{printf"%.2f%%\n", $(NF-2)}'
echo -ne "LAST BOOT: "; who | awk '{printf $3 }' | tr '\n' ' ' && who | awk '{printf $4}'
echo -ne "\nLVM USE: "; if cat /etc/fstab | grep -q "/dev/mapper/"; then echo "yes"; else echo "no";fi
echo -ne "CONNEXIONS TCP: "; cat /proc/net/tcp | wc -l | wak '{print $1-1}' | tr '\n' ' ' && echo "ESTABLISHED"
echo -ne "USER LOG: "; w | wc -l | awk '{print$1-2}'
echo -ne "NETWORK: "; echo -n "IP" && ip route list | grep default | awk '{print $3}' | tr '\n' ' ' && echo -n "9" && ip link show | grep link/ether | awk '{print $2}' | tr '\n' ')' && printf "\n"
echo -ne "SUDO COUNTER: "; journalctl _COMM=sudo | grep COMMAND | wc -l | tr '\n' ' ' && echo Comands
printf "\n"
Caso você queira testar a funcionalidade do script utilize o código abaixo.

$	bash scripts/monitoring.sh

<br><br>
<< [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 9](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_09.md) >>
