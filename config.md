## Criação da VM e Instalação do Sistema Operacional

#### Escolha do Sistema Operacional

É possível escolher entre dois sistemas Operacionais: Debian ou CentOS. No subject do projeto indica que se não há uma experiência em administração de sistemas, que o mais adequado é optar pelo Debian. Motivo pelo qual eu escolhi este Sistema Operacional.

O Debian, pode ser baixado através desse link: https://www.debian.org/

#### Criação da VM



#### Instalação do Sistema Operacional



> Crie um <b>Hostname</b>, sendo ele seu Login + 42.

![alt text](https://user-images.githubusercontent.com/82785772/136550067-b2c83493-613f-4d94-8f63-417c9e67ea3d.png)

> Caso deseje, informe o nome de domínio.

![alt text](https://user-images.githubusercontent.com/82785772/136550144-c367b72a-5a64-443c-9886-7cf3ac7198af.png)

> Crie uma senha para o root, lembrando de seguir a <b>política de senha</b>.<br>
Caso você não tenha criatividade utilize a senha 123Qwedsaz.

![alt text](https://user-images.githubusercontent.com/82785772/136550617-6859ea60-e521-4eaf-8e41-e7cfa2e63705.png)

> Crie um úsuario e em seguida confirme sua senha.

![alt text](https://user-images.githubusercontent.com/82785772/136550803-c4c55a4a-7c78-448b-a60d-b3dec7c5bd83.png)

![alt text](https://user-images.githubusercontent.com/82785772/136550862-d74698b3-52f0-498b-b5af-c20c5be80584.png)

> Configure o fuso horário de sua máquina.<br>
Caso você tenha selecionado o idioma inglês tente localizar um dos fusos mais próximos ao do Brasil.

![alt text](https://user-images.githubusercontent.com/82785772/136551018-fa4378d4-b2b7-4453-a38d-c4bbc2568c12.png)

> Inicie o <b>particionamento de memória</b>, selecionando o modo manual.

![alt text](https://user-images.githubusercontent.com/82785772/136551102-35e56aab-10bf-4676-9c51-130f72ca67b4.png)

> Selecione uma unidade de memória e confirme clicando em <b>sim</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136551254-df0d978a-a8db-4858-951b-f74dacdb3862.png)

> Selecione o <b>espaço livre</b> e <b>crie uma nova partição</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136551406-3f0b0b9c-263f-4c40-b222-14dc77b4eda6.png)

![alt text](https://user-images.githubusercontent.com/82785772/136551458-3f43c36d-f79a-4311-8b4c-0627175b098e.png)

> Defina a <b>quantidade de memória</b>que a primeira partição irá utilizar.<br>
Vale ressaltar que está será a<b>partição responsável pelo boot</b>da máquina, logo, 500MB serão suficientes para essa ação.

![alt text](https://user-images.githubusercontent.com/82785772/136551651-67fac43f-ed2b-4d67-bd04-1630c93c37c3.png)

> Selecione <b>Primária</b> como o tipo da instalação e a defina como <b>Inicial</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136551689-bcb8600c-3f57-48f4-a9f0-ebf37c1effd6.png)

![alt text](https://user-images.githubusercontent.com/82785772/136551722-be4c467f-5461-4074-a0a7-935260a3f1bd.png)

> Nesta etapa será necessário definir dois parâmetros, não sendo necessário alterar os demais.<br>
Em <b>Usar Como</b>, defina <b>ext4 "journaling"</b>.<br>
Em <b>Ponto de Montagem"</b>, defina <b>/boot"</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136551841-2292350a-d963-43a7-a6eb-c936455c854f.png)

> Finalize a partição de memória para o boot.

![alt text](https://user-images.githubusercontent.com/82785772/136551976-bb7f4e8a-6b29-4b0e-9a1b-9647fba64c53.png)

> No espaço restante de memória livre criaremos uma nova partição, fornecendo-a todo o excedente de memória.

![alt text](https://user-images.githubusercontent.com/82785772/136552026-61ae83e1-fec5-418f-b1c5-8ede5bfc2cbf.png)

![alt text](https://user-images.githubusercontent.com/82785772/136552065-ace3c921-4f82-477b-a4fc-52d05afd8a1a.png)

![alt text](https://user-images.githubusercontent.com/82785772/136552139-5b2912a7-e03d-4e1d-8fbf-2325fd01a834.png)

> Selecione <b>Lógica</b> como o tipo da instalação e novamente defina dois parâmetros, não sendo necessário alterar os demais.<br>
Em <b>Usar Como</b>, defina <b>ext4 "journaling"</b>.<br>
Em <b>Ponto de Montagem</b>, defina <b>nenhum</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136552176-3d0e4e1d-050f-4ed8-8f6e-c6365ee6a45a.png)

![alt text](https://user-images.githubusercontent.com/82785772/136552257-f926146d-c588-47d5-9133-342f7681469a.png)

> Finalize a partição de memória.

![alt text](https://user-images.githubusercontent.com/82785772/136552330-04b3ea61-5a99-453b-bf97-03dbe38d18f2.png)

> Selecione a configuração de <b>volumes encriptografados</b> e em seguida selecione <b>sim</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136552434-0763b7cb-1014-4e75-8dc9-b37e05c02ac1.png)

> Crie um novo volume encriptografado, selecionando o <b>slot sda5</b> e finalize o processo sem efetuar nenhuma alteração.<br>
Caso você faça a seleção incorreta da repartição sua máquina apresentará erros futuros.

![alt text](https://user-images.githubusercontent.com/82785772/136552584-796e0334-5999-45aa-992a-fa0ec111e9ce.png)

![alt text](https://user-images.githubusercontent.com/82785772/136552648-e715589d-973e-4252-bf60-41452bcb5011.png)

> Finalize a configuração da partição de memória.

![alt text](https://user-images.githubusercontent.com/82785772/136552731-381da4e7-118a-47be-badb-931e9bae813f.png)

![alt text](https://user-images.githubusercontent.com/82785772/136552777-9a2c9873-e8a4-469d-9adb-eee3c9ae90c7.png)

> Selecione <b>sim</b> e faça a exclusão dos dados.

![alt text](https://user-images.githubusercontent.com/82785772/136552836-f063c5e4-df65-4efe-9670-550f8817fbac.png)

> Crie uma senha/frase para a criptação dos dados.<br>
Lembre-se de seguir a <b>política de senhas</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136555188-8f93f984-6005-4f21-ad11-1165a915d2b4.png)

> Selecione a opção <b>Configuração de volumes lógicos</b> e em seguida selecione <b>sim</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136555493-df677dae-705e-4369-92bd-aad2c28cb0e1.png)

> Crie um novo <b>grupo de volumes</b>, sendo que seu nome deverá ser <b>LVMGroup</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136555670-2e93f591-ae81-4034-bf3a-28cafd6e0e88.png)

![alt text](https://user-images.githubusercontent.com/82785772/136556019-3a88c6ee-a7f0-4b12-b92d-8a2dd6ef79c9.png)

> Selecione a partição criptografada.<br>
Caso você faça a seleção incorreta da repartição sua máquina apresentará erros futuros.

![alt text](https://user-images.githubusercontent.com/82785772/136556110-c06b5407-d7cd-4226-8b97-5a67fa903ab7.png)

> Após criar o grupo de volumes lógicos, iremos criar os volumes em si.<br>
Na opção <b>Criar volume lógico</b>, selecione o grupo que foi criado e em seguida adicione um nome e a quantidade de memória ao novo volume lógico. Os volumes criados deverão ser:<br>
xxx--vg-root, utilizando 2.8GB de memória.<br>
xxx--vg-swap_1, utilizando 976MB de memória.<br>
xxx--vg-home, utilizando 3.8MB de memória.

![alt text](https://user-images.githubusercontent.com/82785772/136556173-ba153ece-80fa-4eb1-a389-e065d8779053.png)

![alt text](https://user-images.githubusercontent.com/82785772/136556215-c55467d2-45e1-4140-85a6-68afc2e72d94.png)

![alt text](https://user-images.githubusercontent.com/82785772/136556781-6f27d45f-af48-4ffe-a1cf-d0590ee5a399.png)

![alt text](https://user-images.githubusercontent.com/82785772/136557085-60ab7a27-850b-43cf-b050-4346fcd8a4cb.png)

> Por fim, após realizar a criação de nossos volumes lógicos, clique em finalizar.

![alt text](https://user-images.githubusercontent.com/82785772/136557910-397f3477-a167-4a3a-b21a-eac789b87afb.png)

> Após a criação de todos nosso volumes lógicos, iremos configura-los, alterando seu <b>Modo de uso</b> e seu<b>Ponto de montagem</b>. Vale lembrar que os demais itens não devem ser alterados.<br>
Defina seu root como: Modo de uso = <b>ext4 "journaling"</b>; <b>Ponto de montagem = /</b>.<br>
Defina seu swap como: Modo de uso = <b>"swap area"</b>.<br>
Defina seu home como: Modo de uso = <b>ext4 "journaling"</b>; <b>Ponto de montagem = /home</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136558144-cd9b9ed8-8728-4010-9653-136437e5a224.png)

![alt text](https://user-images.githubusercontent.com/82785772/136558404-119fd22d-a65a-4f07-a2d6-6358967cd3e8.png)

![alt text](https://user-images.githubusercontent.com/82785772/136558531-193ebab2-9118-4981-9f1f-4a86b166bb7c.png)

> Finalzie essa etapa de configuração dos volumes lógicos e em seguida clique em <b>sim</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136559512-7ec023c7-be64-4b7e-b3ff-456cc0e9d03d.png)

![alt text](https://user-images.githubusercontent.com/82785772/136560590-c8e0cf41-7beb-46cf-8e66-a0d5a7aac138.png)

> Após essa etapa clique em <b>não</b>.<br>
Caso você faça a seleção incorreta sua máquina apresentará erros futuros.

![alt text](https://user-images.githubusercontent.com/82785772/136578558-fdf40607-617a-4c5c-bc16-1862d5df93d2.png)

> Selecione o local do gerenciamento dos pacotes.<br>
Caso sua VM esteja desatualizada a instalação dará erro.

![alt text](https://user-images.githubusercontent.com/82785772/136578618-2a987d7a-8e5e-4b27-915e-c66167d62b54.png)

![alt text](https://user-images.githubusercontent.com/82785772/136582899-f896a260-6a58-44dd-b2e7-de861f86cc7e.png)

> Caso deseje, informe o <b>Proxy</b>.

![alt text](https://user-images.githubusercontent.com/82785772/136582976-2bbaa7e0-f6aa-49f6-98de-d9de061c10f1.png)

> Após essa etapa clique em <b>não</b>.<br>
Caso você faça a seleção incorreta sua máquina apresentará erros futuros.

![alt text](https://user-images.githubusercontent.com/82785772/136585259-4abcdcd3-256e-4efa-a2cd-a7ae0060796f.png)

> Caso algum item tenha sido marcado, retire todas as marcações.

![alt text](https://user-images.githubusercontent.com/82785772/136585483-ce5d453d-b18e-44da-99a8-1a409c663776.png)

> Para realizar a instalação do GRUB seguida clique em <b>sim</b> e selecione o dispositivo a ser instalado.

![alt text](https://user-images.githubusercontent.com/82785772/136585889-f8174a96-cb90-4f02-a081-4043d214ddc0.png)

![alt text](https://user-images.githubusercontent.com/82785772/136586361-8f28255b-d97f-4ed7-bc5c-92853a3039a4.png)

> Finalzie a instalação do Debian e comece a utilizar sua VM.

![alt text](https://user-images.githubusercontent.com/82785772/136586555-1bf0dcd2-6d5b-4886-86ef-7be4f6f97d0c.png)

