<< [Parte 3](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_03.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) >>
<br><br>

## Parte 4: Instalação do SSH

1. Para instalar o SSH.

   `apt install openssh-server`

2. Verifique a instalação do SSH.

   `dpkg -l | grep ssh`

3. Configurar o ssh

   `nano etc/ssh/sshd_config`
   
4. Retire o comentário da linha 13: #Port 22.

   `Port 4242`
   
5. Altere a linha 32: #PermitRootLogin prohibit-password para    

   `PermitRootLogin no`
   
6. Verifique se as alterações foram feitas

   `service ssh status`

7. Para verificar o ip da máquina

   `ip addr show`
   
   Será o numero IP que aparece no segundo bloco de informações
   
8. Para acessar via SSH de outro terminal

   `ssh <username>@<ip-address> -p 4242`
   
9. Para deslogar

   `logout`
   
   ou 
   
   `sair`

<br><br>
<< [Parte 3](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_03.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) >>
