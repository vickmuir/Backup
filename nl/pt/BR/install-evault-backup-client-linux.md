---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Instalando o EVault Backup Client no Linux 

A instalação do EVault Backup Client em um sistema operacional baseado em Linux pode ser feita por
meio de uma série de comandos no shell ou no terminal dentro do S.O. Este procedimento descreve as etapas necessárias
para instalar o EVault Backup Client em qualquer um dos seguintes sistemas operacionais baseados em
Linux:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

Após o procedimento ser concluído, o processo automatizado registra o serviço do agente com o
WebCC e, em seguida, faz download e instala os arquivos necessários para executar o serviço. Siga as etapas abaixo
para instalar o EVault Backup Client para o S.O. baseado em Linux.

**Nota**: se você comprou o EVault quando solicitou um servidor no
{{site.data.keyword.slportal}}, então o software é instalado automaticamente para você e não
é necessário usar os procedimentos descritos neste documento.

Se você comprou o EVault como um Upgrade no {{site.data.keyword.slportal}}, siga estas etapas para
instalar o software.

## Efetue login no servidor de dispositivo de destino

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e selecione **Dispositivos** > **Lista de dispositivos** no menu principal para ver a lista de dispositivos do servidor disponíveis.
2. Localize o dispositivo para o qual você comprou o serviço do EVault e anote o seu endereço IP público. 
Ele deve ser usado nas etapas a seguir ao efetuar login no dispositivo por meio de uma linha de comandos do
UNIX ou do Linux. Substitua <publicIpAddress> pelo endereço IP público real nos comandos seguintes. 
3. Clique na seta de expansão apontada para a direita para revelar informações adicionais sobre o
dispositivo, incluindo o nome do usuário e a senha.  Se a senha não for exibida, clicar na caixa de seleção
**Mostrar senha** vai revelá-la. O nome do usuário e a senha serão usados na próxima etapa para efetuar login
no dispositivo de teste.  Substitua `<user name>` pelo nome do usuário real nos comandos a
seguir.
4. Efetue login no dispositivo de destino usando ssh executando o comando a seguir em uma
linha de comandos do Unix ou do Linux:
  ```
  ssh <user name>@<publicIpAddress>
  ```
  {: pre}
  
 **Nota**: se você não efetuou login nesse servidor com esse nome do usuário antes,
será exibida uma mensagem sobre a autenticidade do host e será perguntado se você deseja continuar.  Responda com **sim** para continuar.
5. Será solicitado a inserir a senha, a menos que você tenha configurado anteriormente as chaves
SSH para o acesso a esse servidor.

## Atualize o Linux para preparar-se para a instalação do cliente do EVault (somente RedHat Linux)
**Nota**: essa etapa é necessária para o RedHat Linux, mas opcional para outras
distribuições do Linux.

- Execute o comando a seguir no prompt do servidor:
  ```
  Yum update
  ```
  {: pre}
   
  Se solicitado, confirme que o tamanho do download está adequado. A atualização continuará e exibirá
uma mensagem "Concluído!" quando terminar.

## Obter o Script de Instalação EVault
- Execute o comando a seguir no prompt do servidor:
  ```
  -N wget http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Execute o script de instalação do EVault
1. Execute o seguinte comando no prompt do servidor:
  ```
  ./evault_manual.sh sh
  ```
  {: pre}

2. Insira seu nome do usuário e senha do WebCC.     
  **Nota**: consulte o artigo [Introdução
aos serviços de backup](/docs/infrastructure/Backup/index.html) para obter instruções para visualizar o nome do usuário e a senha do EVaultbackup.
3. Após o nome do usuário e a senha, nenhuma entrada adicional é necessária, mesmo que alguns
prompts sejam exibidos na tela conforme a instalação continua. Esses avisos podem ser ignorados com segurança. 
Eles estão sendo produzidos por um subscript que é chamado pelo script *evault_manual.sh*.  O
script *evault_manual.sh* fornece a entrada para esses prompts.
4. Quando mensagens semelhantes às seguintes aparecem, a instalação foi concluída:
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## Verifique se a Instalação Bem-sucedida
1. Verifique se a mensagem "Registrado no portal." aparece na saída de instalação. Isso pode ser feito
procurando pela mensagem na tela ou inspecionando a saída do comando a seguir:
  ```
  Grep 'Registrado' /opt/BUAgent/Install.log
  ```
  {: pre}

2. Execute o comando a seguir e observe a saída: 
  ```
  Status vvagent de serviço
  ```
  {: pre}
   
  As seguintes mensagens devem ser exibidas:
  ```
  VVAgent está em execução (PID xxxxx).
  Buagent está em execução (PID xxxxx).
  ```
  {: codeblock}
   
  **Nota**: os IDs de processo representados acima por 'xxxxx' variam com cada
instalação. 
  
## Etapas Seguintes

Efetue login no WebCC para configurar e gerenciar os seus agentes de backup. Consulte o [Tutorial de Introdução](index.html#configuring-evault-agent-in-webcc) para obter instruções.
