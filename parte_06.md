<< [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) >>
<br><br>

## Parte 6: Instalação e configuração do sudo

1. Instalação do sudo.

   `apt-get install sudo`
   
2. Verifique a instalação do sudo.

   `dpkg -l | grep sudo`
   
3. Adicionar um usuário ao sudo

   `gpasswd -a <username> sudo`
   
4. Verifique se o úsuario foi adicionado corretamente ao grupo Sudo.

   `getent group sudo`
   
5. É necessário fazer o logout e login novamente



$	reboot
$	sudo -v
Verifique os privilégios do grupo Sudo.

$	sudo apt update
Caso necessário é possível remover um úsuario do grupo Sudo.

$	gpasswd -d <username> sudo
Configurando o Sudo
Crie um novo diretório para registrar os logins e logouts do grupo.

$	sudo mkdir /var/log/sudo
Abra o arquivo de configuração do Sudo, tanto através do comando ou do diretório.

$	sudo visudo -f etc/sudoers.d/<file>	# acessar as confgs do sudo através do diretório
$	sudo visudo				# comando para acessar as confgs do sudo
Configure as tentativas de autentificações de entrada.

Defaults	passwd_tries = 3
Defaults	badpass_message = "WRONG PASSWORD"
Registre os logins e logouts do grupo.

Defaults	logfile="/var/log/sudo/<filename>"
Defaults	log_input, log_output
Defaults	iolog_dir="/var/log/sudo"
Adicione o Requiretty, habilitando o modo TTY.

Defaults	requiretty
Por fim, altere o caminho do secure_path.

O antigo caminho será secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin:

Defaults	secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
  
<br><br>
<< [Parte 5](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_05.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 7](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_07.md) >>
