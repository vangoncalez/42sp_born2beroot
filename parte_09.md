<< [Parte 8](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_08.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Inicial](https://github.com/vangoncalez/42sp_born2beroot) 
<br><br>

## Parte 9: Bonus

#### Lighttpd

1. Instalação do Lighttpd

    `sudo apt-get install lighttpd`
    
2. Verifique se foi corretamente instalado

    `dpkg -l | grep lighttpd`
    
3. Permita a porta 80 no UFW

    `sudo ufw allow 80`
    
    
    
<br><br>
#### MariaDB 

1. Instalação do MariaDB

    `sudo apt-get install mariadb-server`

2. Verifique se foi corretamente instalado

    `dpkg -l | grep mariadb-server`
    
3. Inicie o script de instalação segura do Mysql

    `sudo mysql_secure_installation`
    
    Serão solicitadas algumas informações:
    ```
    Enter current password for root (enter for none): 
    Set root password? [Y/n] n
    Remove anonymous users? [Y/n] Y
    Disallow root login remotely? [Y/n] Y
    Remove test database and access to it? [Y/n] Y
    Reload privilege tables now? [Y/n] Y
    ```
    
4. Faça o login no MariaDB

    `sudo mariadb`

5. Crie um banco de dados

    `CREATE DATABASE <database-name>;`
    
6. Crie um novo usuário para o banco de dados e dê privilégio total

    `GRANT ALL ON <database-name>.* TO '<new_user>'@'localhost' IDENTIFIED BY '<password>' WITH GRANT OPTION;`

7. Reinicie os novos privilégios

    `FLUSH PRIVILEGES;`
    
8. Faça logout do MariaDB

    `exit`
    
9. Faça login com o novo usuário para fazer um teste se está funcionando

    `mariadb -u <new_user> -p`
    
10. Verifique se a base de dados foi realmente criada

    `SHOW DATABASES;`

11. Faça logout do MariaDB

    `exit`
<br><br>
#### PHP 

1. Instalação do PHP

    `sudo apt install php-cgi php-mysql`

2. Verifique se foi corretamente instalado

    `dpkg -l | grep php`
    
<br><br>
#### WordPress 

1. Instalação do wget

    `sudo apt install wget`
    
2. Download do WordPress

    `sudo wget http://wordpress.org/latest.tar.gz -P /var/www/html`
    
3. Descompressão do arquivo tar

    `sudo tar -xzvf /var/www/html/latest.tar.gz`
    
4. Remoção do arquivo tar    

    `sudo rm /var/www/html/latest.tar.gz`
    
5. Copiar o conteúdo da pasta wordpress para a pasta acima  

    `sudo cp -r /var/www/html/wordpress/* /var/www/html`
    
6. Remover a pasta wordpress vazia

    `sudo rm -rf /var/www/html/wordpress`

7. Copiar o arquivo modelo de configuração do wordpress

    `sudo cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php`

8. Alterar o arquivo de configuração do wordpress

    `sudo nano /var/www/html/wp-config.php`
    
    Alterar as informações abaixo com as informaçõe criadas

    ```
    define( 'DB_NAME', '<database-name>' );
    define( 'DB_USER', '<novo_usuario>' );
    define( 'DB_PASSWORD', '<password>' );
    ```
  
 9. Configurar o lighttpd para o php

    `sudo lighty-enable-mod fastcgi`

    `sudo lighty-enable-mod fastcgi-php`
    
    `sudo service lighttpd force-reload`
  
<br><br>
#### FTP 

1. Instalação do wget

    `sudo apt install vsftpd`

2. Verifique se foi corretamente instalado

    `dpkg -l | grep vsftpd`
    
3. Permitir porta 21

    `sudo ufw allow 21`
    

4. Para criar uma pasta para algum usuário acessar via ftp

    Para criar uma pasta
    
    `sudo mkdir /home/<username>/ftp`
    
    `sudo mkdir /home/<username>/ftp/files`
    
    Para alterar o "dono" da pasta 
    
    `sudo chown nobody:nogroup /home/<username>/ftp`
    
    Para alterar a permissão da pasta 
    
    `sudo chmod a-w /home/<username>/ftp`

5. Alterar arquivo de configuração     

    `sudo nano /etc/vsftpd.conf`
    
    descomentar a linha abaixo:

    `#write_enable=YES`
    
    acrescentar as linhas abaixo para encaminhar o usuário para a pasta:
    
    ```
    user_sub_token=$USER
    local_root=/home/$USER/ftp
    ```
    
    Para previnir o usuário de acessar arquivos fora da arvore do diretório
   
    `#chroot_local_user=YES`
    
6. Para acessar via ftp 

    `ftp <ip-address>`
    
    

<br><br>
<< [Parte 8](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_08.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Inicial](https://github.com/vangoncalez/42sp_born2beroot) 
