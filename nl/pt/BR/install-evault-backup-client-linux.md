---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}

# Instalando o EVault Backup Client no Linux 

A instalação do EVault Backup Client em um sistema operacional baseado em Linux pode ser feita por meio de uma série de comandos no shell ou no terminal dentro do S.O. Este procedimento descreve as etapas que são necessárias para instalar o cliente de backup do EVault em qualquer um dos sistemas operacionais baseados em Linux a seguir:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

Depois de concluir o procedimento, o processo automatizado registra o serviço de Agente com o WebCC e, em seguida, faz download e instala os arquivos necessários para executar o serviço.

>**Nota**: se você comprou o EVault ao solicitar um servidor no {{site.data.keyword.slportal}}, o software será instalado automaticamente para você. Não é necessário usar os procedimentos que estão descritos neste documento.

Se você comprou o EVault como um Upgrade no {{site.data.keyword.slportal}}, siga estas etapas para
instalar o software.

## Efetuando login no servidor de dispositivo de destino

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e selecione **Dispositivos** > **Lista de dispositivos** no menu principal para ver a lista de dispositivos do servidor disponíveis.
2. Localize o dispositivo para o qual você comprou o serviço do EVault e anote seu endereço IP público. 
  - Esse endereço IP deve ser usado nas etapas a seguir quando você efetuar login no dispositivo em uma linha de comandos do UNIX ou Linux. Substitua
<publicIpAddress> pelo endereço IP público real no comando que é mostrado na Etapa 4. 
3. Clique na seta que aponta para a direita para exibir mais informações sobre o dispositivo, incluindo o nome do usuário e a senha. 
  - Se a senha não for exibida, ela poderá ser revelada clicando em **Mostrar senha**. O nome do usuário e a senha são usados na próxima etapa para efetuar login no dispositivo de teste. Substitua `<user name>` pelo nome do usuário real.
4. Efetue login no dispositivo de destino inserindo o comando a seguir em uma linha de comandos UNIX ou Linux.
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}
   
   >**Nota**: se você não efetuou login nesse servidor com esse nome de usuário antes, será exibida uma mensagem sobre a autenticidade do host. Também será perguntado se você deseja continuar. Responda com **sim** para continuar.
5. Será solicitado para você inserir a senha, a menos que você configure as chaves SSH para acessar esse servidor antes.

## Atualizando o Linux para preparar-se para instalar o cliente EVault (somente RedHat Linux)
>**Nota**: essa etapa é necessária para o RedHat Linux, mas opcional para outras distribuições do Linux.

- Execute o comando a seguir no prompt do servidor.
  ```
  yum update
  ```
  {: pre}
   
  Se for solicitado, confirme se o tamanho do download está correto. A atualização continua e exibe uma mensagem "Concluído!" quando ela é concluída.

## Obtendo o script de instalação do EVault

- Execute o comando a seguir no prompt do servidor.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Executando o script de instalação do EVault

1. Execute o comando a seguir no prompt do servidor.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Insira seu nome do usuário e senha do WebCC.     
   >**Nota**: consulte o artigo [Introdução aos serviços de backup](/docs/infrastructure/Backup/index.html) para obter instruções para visualizar o nome do usuário e a senha do backup do EVault.
3. Após o nome do usuário e a senha, nenhuma entrada adicional será necessária, embora alguns prompts sejam escritos na tela conforme a instalação continua. Esses avisos podem ser ignorados com segurança. Eles estão sendo produzidos por um subscript, que é iniciado pelo script `evault_manual.sh`. O
script `evault_manual.sh` fornece a entrada para esses prompts.
4. Quando mensagens semelhantes às seguintes aparecem, a instalação foi concluída:
   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}
   
## Verificando se a Instalação foi Bem-sucedida

1. Verifique se a mensagem "Registrado no portal." aparece na saída de instalação. A verificação pode ser feita procurando a mensagem na tela ou inspecionando a saída do comando a seguir:
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. Execute o comando a seguir e observe a saída.
   ```
   service vvagent status
   ```
   {: pre}
   
   As mensagens a seguir são exibidas.
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}
   
  >**Nota**: os IDs do processo representados por `xxxxx` variam com cada instalação. 
  
**Etapas seguintes**

Efetue login no WebCC para configurar e gerenciar seus agentes de backup. Consulte o [Tutorial de introdução](index.html#configuring-evault-agent-in-webcc) para obter instruções.
