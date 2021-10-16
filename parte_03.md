<< [Parte 2](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_02.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 4](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_04.md) >>
<br><br>

## Configuração da VM

### Configuração Básica

1. Informe o <b>Hostname</b>. Ele deverá ser o seu Login + 42.

![alt text](https://user-images.githubusercontent.com/82785772/136550067-b2c83493-613f-4d94-8f63-417c9e67ea3d.png)

2. O nome de domínio não será necessário nesse projeto.

![alt text](https://user-images.githubusercontent.com/82785772/136550144-c367b72a-5a64-443c-9886-7cf3ac7198af.png)

3. Defina uma senha para o root. Siga a política de senhas que o subject sugere.

![alt text](https://user-images.githubusercontent.com/82785772/136550617-6859ea60-e521-4eaf-8e41-e7cfa2e63705.png)

4. Agora vamos criar um novo usuário. Escreva o nome completo do usuário.

![alt text](https://user-images.githubusercontent.com/82785772/136550803-c4c55a4a-7c78-448b-a60d-b3dec7c5bd83.png)

5. E digite uma senha

![alt text](https://user-images.githubusercontent.com/82785772/136550862-d74698b3-52f0-498b-b5af-c20c5be80584.png)

6. Neste passo vamos configurar o fuso horário

![alt text](https://user-images.githubusercontent.com/82785772/136551018-fa4378d4-b2b7-4453-a38d-c4bbc2568c12.png)

### Particionamento da memória

1. Selecione manual

![alt text](https://user-images.githubusercontent.com/82785772/136551102-35e56aab-10bf-4676-9c51-130f72ca67b4.png)

2. Selecione a unidade de memória

![alt text](https://user-images.githubusercontent.com/82785772/136551254-df0d978a-a8db-4858-951b-f74dacdb3862.png)

3. Selecione o espaço livre para criar a partição. 

![alt text](https://user-images.githubusercontent.com/82785772/136551406-3f0b0b9c-263f-4c40-b222-14dc77b4eda6.png)

4. Em seguida selecione criar uma nova partição

![alt text](https://user-images.githubusercontent.com/82785772/136551458-3f43c36d-f79a-4311-8b4c-0627175b098e.png)

5. A primeira partição será destinada ao Boot. Setaremos conforme a estrutura do Bonus do Subject. Reservaremos um espaço de 500M.

![alt text](https://user-images.githubusercontent.com/82785772/136551651-67fac43f-ed2b-4d67-bd04-1630c93c37c3.png)

6. Primária

![alt text](https://user-images.githubusercontent.com/82785772/136551689-bcb8600c-3f57-48f4-a9f0-ebf37c1effd6.png)

7. Inicial

![alt text](https://user-images.githubusercontent.com/82785772/136551722-be4c467f-5461-4074-a0a7-935260a3f1bd.png)

8. Na próxima tela, dois parâmetros deverão ser ajustados:
Em <b>Usar Como</b>, defina <b>ext4 "journaling"</b>.<br>
Em <b>Ponto de Montagem"</b>, defina <b>/boot"</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136551841-2292350a-d963-43a7-a6eb-c936455c854f.png)

8. Selecione Finalizar

![alt text](https://user-images.githubusercontent.com/82785772/136551976-bb7f4e8a-6b29-4b0e-9a1b-9647fba64c53.png)

9. Selecione o espaço livre para criar uma nova partição.

![alt text](https://user-images.githubusercontent.com/82785772/136552026-61ae83e1-fec5-418f-b1c5-8ede5bfc2cbf.png)

10. Selecione criar uma nova partição

![alt text](https://user-images.githubusercontent.com/82785772/136552065-ace3c921-4f82-477b-a4fc-52d05afd8a1a.png)

11. Escreva "max" para definir todo o restante de espaço para essa nova partição

![alt text](https://user-images.githubusercontent.com/82785772/136552139-5b2912a7-e03d-4e1d-8fbf-2325fd01a834.png)

12. Selecione lógica

![alt text](https://user-images.githubusercontent.com/82785772/136552176-3d0e4e1d-050f-4ed8-8f6e-c6365ee6a45a.png)

13. Altere os parâmetros da tela seguinte para:
Em <b>Usar Como</b>, defina <b>ext4 "journaling"</b>.<br>
Em <b>Ponto de Montagem</b>, defina <b>nenhum</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136552257-f926146d-c588-47d5-9133-342f7681469a.png)

14. Finalize a partição de memória

![alt text](https://user-images.githubusercontent.com/82785772/136552330-04b3ea61-5a99-453b-bf97-03dbe38d18f2.png)

15. Selecione a configuração de <b>volumes encriptografados</b> e em seguida selecione <b>sim</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136552434-0763b7cb-1014-4e75-8dc9-b37e05c02ac1.png)

16. Selecione Criar volumes criptografados

![alt text](https://user-images.githubusercontent.com/82785772/136552584-796e0334-5999-45aa-992a-fa0ec111e9ce.png)

17. Selecionando o <b>slot sda5</b> e finalize

![alt text](https://user-images.githubusercontent.com/82785772/136552648-e715589d-973e-4252-bf60-41452bcb5011.png)

18. Clique em finalizar

![alt text](https://user-images.githubusercontent.com/82785772/136552731-381da4e7-118a-47be-badb-931e9bae813f.png)

![alt text](https://user-images.githubusercontent.com/82785772/136552777-9a2c9873-e8a4-469d-9adb-eee3c9ae90c7.png)

19. Selecione <b>sim</b> e faça a exclusão dos dados.

![alt text](https://user-images.githubusercontent.com/82785772/136552836-f063c5e4-df65-4efe-9670-550f8817fbac.png)

20. Crie uma senha/frase para a criptação dos dados. Lembre-se de seguir a <b>política de senhas</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136555188-8f93f984-6005-4f21-ad11-1165a915d2b4.png)

21. Selecione a opção <b>Configuração de volumes lógicos</b> e em seguida selecione <b>sim</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136555493-df677dae-705e-4369-92bd-aad2c28cb0e1.png)

22. Crie um novo <b>grupo de volumes</b>: <b>LVMGroup</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136555670-2e93f591-ae81-4034-bf3a-28cafd6e0e88.png)

![alt text](https://user-images.githubusercontent.com/82785772/136556019-3a88c6ee-a7f0-4b12-b92d-8a2dd6ef79c9.png)

23. Selecione a partição criptografada.<br>

![alt text](https://user-images.githubusercontent.com/82785772/136556110-c06b5407-d7cd-4226-8b97-5a67fa903ab7.png)

24. Clique em <b>criar volume lógico</b>

![alt text](https://user-images.githubusercontent.com/82785772/136556173-ba153ece-80fa-4eb1-a389-e065d8779053.png)

25. Selecione o grupo de volumes

![alt text](https://user-images.githubusercontent.com/82785772/136556215-c55467d2-45e1-4140-85a6-68afc2e72d94.png)

26. Defina o nome para o volume lógico

![alt text](https://user-images.githubusercontent.com/82785772/136556781-6f27d45f-af48-4ffe-a1cf-d0590ee5a399.png)

27. Defina o tamanho ocupado do volume lógico

![alt text](https://user-images.githubusercontent.com/82785772/136557085-60ab7a27-850b-43cf-b050-4346fcd8a4cb.png)

28. Repita o processo dos itens 24 a 27 para criar cada um dos demais volumes lógicos

29. Clique em finalizar

![alt text](https://user-images.githubusercontent.com/82785772/136557910-397f3477-a167-4a3a-b21a-eac789b87afb.png)

30. Após a criação de todos nosso volumes lógicos, deve-se alterar seu <b>Modo de uso</b> e seu<b>Ponto de montagem</b>
Defina root como: Modo de uso = <b>ext4 "journaling"</b>; <b>Ponto de montagem = /</b>.<br>
Defina swap como: Modo de uso = <b>"swap area"</b>.<br>
Defina home como: Modo de uso = <b>ext4 "journaling"</b>; <b>Ponto de montagem = /home</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136558144-cd9b9ed8-8728-4010-9653-136437e5a224.png)

![alt text](https://user-images.githubusercontent.com/82785772/136558404-119fd22d-a65a-4f07-a2d6-6358967cd3e8.png)

![alt text](https://user-images.githubusercontent.com/82785772/136558531-193ebab2-9118-4981-9f1f-4a86b166bb7c.png)

31. Clique em finalizar e em seguida clique em sim.

![alt text](https://user-images.githubusercontent.com/82785772/136559512-7ec023c7-be64-4b7e-b3ff-456cc0e9d03d.png)

![alt text](https://user-images.githubusercontent.com/82785772/136560590-c8e0cf41-7beb-46cf-8e66-a0d5a7aac138.png)

32. Clique em não

![alt text](https://user-images.githubusercontent.com/82785772/136578558-fdf40607-617a-4c5c-bc16-1862d5df93d2.png)

33. Selecione a localização do gerenciador de pacotes

![alt text](https://user-images.githubusercontent.com/82785772/136578618-2a987d7a-8e5e-4b27-915e-c66167d62b54.png)

34. Selecione o espelho do gerenciador de pacotes

![alt text](https://user-images.githubusercontent.com/82785772/136582899-f896a260-6a58-44dd-b2e7-de861f86cc7e.png)

35. O Proxy nesse projeto pode permaneceer vazio

![alt text](https://user-images.githubusercontent.com/82785772/136582976-2bbaa7e0-f6aa-49f6-98de-d9de061c10f1.png)

36. Clique em não

![alt text](https://user-images.githubusercontent.com/82785772/136585259-4abcdcd3-256e-4efa-a2cd-a7ae0060796f.png)

37. Retire todas as marcações

![alt text](https://user-images.githubusercontent.com/82785772/136585483-ce5d453d-b18e-44da-99a8-1a409c663776.png)

38. Clique em sim para a instalação do GRUB 

![alt text](https://user-images.githubusercontent.com/82785772/136585889-f8174a96-cb90-4f02-a081-4043d214ddc0.png)

39. Selecione o dispositivo onde será instalado o GRUB

![alt text](https://user-images.githubusercontent.com/82785772/136586361-8f28255b-d97f-4ed7-bc5c-92853a3039a4.png)

40. Finalize a instalação

![alt text](https://user-images.githubusercontent.com/82785772/136586555-1bf0dcd2-6d5b-4886-86ef-7be4f6f97d0c.png)

<br><br>
<< [Parte 2](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_02.md) &nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp; [Parte 4](https://github.com/vangoncalez/42sp_born2beroot/blob/main/parte_04.md) >>

