<< [Parte 3](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_03.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) >>
<br><br>

## Parte 4: Instalação do SSH

1. Para instalar o SSH.

   `apt install openssh-server`

2. Verifique a instalação do SSH.

   `dpkg -l | grep ssh`

3. Configurar o ssh

   `nano etc/ssh/ssh_config`
   
4. Retire o comentário da linha 13: #Port 22.

   `Port 4242`
   
5. Altere a linha 32: #PermitRootLogin prohibit-password para    

   `PermitRootLogin no`
   
6. Verifique se as alterações foram feitas

   `service ssh status`


<br><br>
<< [Parte 3](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_03.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) >>
