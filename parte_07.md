<< [Parte 6](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_06.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 8](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_08.md) >>
<br><br>

## Parte 7: Política de Senhas e Gerenciamento de Usuários e Grupos

1. Configurações de Senha

   Acesse o arquivo de configuração

   `nano /etc/login.defs`
   
   Altere a linha 160: tempo em dias para a senha expirar 

   `PASS_MAX_DAYS   30`
   
   Altere a linha 161: tempo em dias que a senha pode ser alterada antes de expirar

   `PASS_MIN_DAYS   2`
   
   Altere a linha 162: tempo em dias para a mensagem de alerta antes da senha expirar

   `PASS_WARN_AGE   7`
   <br><br>
   
2. Política de Senhas Forte - Instalação do lib-pwquality  

   `apt install libpam-pwquality`

    Verifique a instalação:
    
   `dpkg -l | grep libpam-pwquality`
   
    Acesse o arquivo de configuração

   `nano /etc/pam.d/common-password`
   
    Linha 25: acrescentar as regras:
    
   ```password	requisite	pam_pwquality.so retry=3 minlen=10 ucredit=-1 dcredit=-1 maxrepeat=3 reject_username difok=7 enforce_for_root```
   
   <br>
   
   | Política  |      Descrição      |  
   |:---------|:--------------|
   | retry=3 | número máximo de tentativas | 
   | minlen=10 | tamanho mínimo de caracteres da senha   |   
   | ucredit=-1 | pelo menos uma letra maiúscula |   
   | dcredit=-1 | pelo menos um número |   
   | maxrepeat=3 |  não pode ter mais que 3 caracteres idênticos consecutivos |   
   | reject_username | não pode incluir o nome do usuário |   
   | difok=7  | não pode repetir 7 dos caracteres da senha anterior |   
   | enforce_for_root  | o root deve obedecer os mesmos critérios |         
<br><br>

3. Gerenciamento de usuários

   Para adicionar um usuário:

   `adduser <username>`

   Para deletar um usuário

   `deluser <username>`

   Para verificar a existência de um úsuario:

   `getent passwd <username>`
   
   Para verificar quanto tempo falta para que uma senha de um úsuario esteja prestes a expirar utilize:

   `chage -l <username>`
<br><br>

4. Gerenciamento de grupos

   Para criar um grupo:
  
   `addgroup <group_name>`
  
   Para apagar um grupo:
  
   `delgroup <group_name>`
  
   Para verificar os grupos existentes:
   `cat etc/group`
   
   Para adicionar um usuário a um grupo:
   
   `gpasswd -a <username> <group_name>`
   
   Para verificar se um úsuario foi corretamente adicionado a um grupo:

   `getent group user42`
   
  
<br><br>
<< [Parte 6](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_06.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 8](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_08.md) >>

