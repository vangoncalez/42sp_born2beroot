<< [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) >>
<br><br>

## Parte 6: Instalação e configuração do sudo

#### Instalação do sudo

1. Instalação do sudo.

   `apt-get install sudo`
   
2. Verifique a instalação do sudo.

   `dpkg -l | grep sudo`
   
   
<br>   <br>  
#### Adicionar ou remover usuários do sudo  
   
1. Adicionar um usuário ao sudo

   `adduser <username> sudo`
   
2. Deletar um usuário do sudo

   `deluser <username> sudo`
   
3. Verifique se o úsuario foi adicionado ou deletado corretamente ao grupo Sudo.

   `getent group sudo`
   
4. Talvez seja necessário reiniciar a máquina

   `reboot`
   
   
   
#### Configurar o sudo     

1. Crie a pasta onde serão salvos todas os comandos executados via sudo

   `sudo mkdir /var/log/sudo`

2. Abra o arquivo de configuração

   `sudo visudo`

   Acrescente as linhas ao arquivo:<br>  
   
   Para limitar a 3 tentativas:<br>  
   `Defaults	passwd_tries = 3`<br>  <br>  
   
   Para retornar uma mensagem de erro, quando o usuário digitar a senha errada:<br>  
   `Defaults	badpass_message = "Wrong Password, padawan!"`<br>  <br>  
   
   Para salvar todos os acessos via sudo<br>  
   `Defaults	logfile="/var/log/sudo/sudo.log"`<br>  
   `Defaults	log_input, log_output`<br>  
   `Defaults	iolog_dir="/var/log/sudo"`<br>  <br>  
   
   Para solicitar TTY<br>  
   `Defaults	requiretty`<br>  <br>  
   
   Para definir local do sudo<br>  
   `Defaults	secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"`<br>  <br>  
  
<br><br>
<< [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) >>
