<< [Parte 4](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_04.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 6](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_06.md) >>
<br><br>

## Parte 5: Instalando e Configurando o UFW

1. Instalação do UFW.

   `apt install ufw`
   
2. Verifique se foi corretamente instalado

   `dpkg -l | grep ufw`
   
3. Habilite o UFW.

   `ufw enable`
   
4. Permita conexões na porta 4242.

   `ufw allow 4242`
   
5. Verifique o status

   `ufw status`

6. Se você tiver fazendo o Bonus, deve permitir conexões na porta 80

   `ufw allow 80`

<br><br>
<< [Parte 4](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_04.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 6](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_06.md) >>
