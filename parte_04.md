## Instalação do SSH

1. Para instalar o SSH.

  `apt install openssh-server`

2. Verifique a instalação do SSH.

>dpkg -l | grep ssh

Acesse o diretório em que o SSH foi instalado e comece a configurar o programa.

$	nano etc/ssh/ssh_config
As configurações do SSH são simples e exigem pequenas alterações nas linahs de código já existentes.

Na linha 13 teremos o comentário: #Port 22.

13	Port 4242
Na linha 32 teremos co comentário: #PermitRootLogin prohibit-password.

32	PermitRootLogin no
Por fim verifique se as modificações foram bem sucedidas.

$	service ssh status
