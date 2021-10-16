<< [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 9](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_09.md) >>
<br><br>

## Parte 8: Cron

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
   | #Disk Usage | através do comando df ?????? |
   | #CPU load | através do comando top -b -n1, buscando a linha que contém o Cpu |
   | #Last boot | através do comando who -b |
   | #LVM use | Com o comando lsblk é possível ver as unidades type lvm. Podemos fazer uma condicional caso encontre o lvm e printar yes |
   | #Connexions TCP | através do comando netstat, é possível verificar as conexões. Para usar esse comando, uma instalação é necessária, veja na sequência. |
   | #User log | através do comando who, é possível saber os usuários logados. Podemos fazer um script para contar quantos usuários |
   | #Network | Através de "hostname -I" e "ip a" é possível obter o ipv4 e o MAC |
   | #Sudo | Para contar quantos sudos há no log, podemos usar um grep -c 'COMMAND' <nome do arquivo> |
   
   
  Para testar o script enquanto o desenvolve basta executá-lo via bash ou sh
  
   `sh scripts/monitoring.sh`
   
<br><br> 

4. Para instalar o netstat
   
   `apt-get update`
   
   `apt-get install net-tools`
  <br><br>  
5. Wall
   
   Para usar o wall, basta acrescentar no arquivo de script:
   
   wall "
   <informação a ser impressa na tela>
   "
   
   <br><br> 
6. Acesse as configurações do Cron

   `crontab -e`
<br><br>    
7. Acrescente uma regra para que um script seja executado a cada 10 minutos

   `*/10 * * * * sh /path/to/script`
 <br><br>   
 

<br><br>
<< [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 9](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_09.md) >>
