---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Linux

subcollection: Backup

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalando o cliente de backup no Linux
{: #InstallinLinux}

A instalação do cliente do {{site.data.keyword.backup_full}} em um sistema operacional baseado em
Linux pode ser feita por meio de uma série de comandos no shell ou no terminal dentro do S.O. Esse procedimento descreve as etapas necessárias para instalar o cliente em qualquer um dos sistemas operacionais baseados em Linux a seguir:

- RHEL
- CentOS
- CloudLinux

Depois que você conclui o procedimento, o processo automatizado registra o serviço do Agente com o portal do {{site.data.keyword.backup_notm}} e, em seguida, faz download e instala os arquivos necessários para executar o serviço.

Se você tiver comprado o {{site.data.keyword.backup_notm}} quando pediu um servidor por meio do [catálogo do {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} ou do {{site.data.keyword.slportal}}, o software será instalado automaticamente para você. Não é necessário usar os procedimentos que estão descritos neste documento.
{:tip}

Se você comprou o {{site.data.keyword.backup_notm}} como um upgrade no
{{site.data.keyword.slportal}}, sigas estas etapas para instalar o software.

## Efetuando login no servidor de dispositivo de destino
{: #logintargetLin}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.<br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Selecione **Dispositivos** > **Lista de dispositivos** no menu principal para ver a lista de dispositivos do servidor disponíveis.
3. Localize o dispositivo para o qual você comprou o serviço do {{site.data.keyword.backup_notm}} e anote seu endereço IP público.
  - Esse endereço IP deve ser usado nas etapas a seguir quando você efetuar login no dispositivo em uma linha de comandos do UNIX ou Linux. Substitua <publicIpAddress> pelo endereço IP público real no comando que é mostrado na Etapa 5.
4. Clique na seta que aponta para a direita para exibir mais informações sobre o dispositivo, incluindo o nome do usuário e a senha.
  - Se a senha não for exibida, ela poderá ser revelada clicando em **Mostrar senha**. O nome do usuário e a senha são usados na próxima etapa para efetuar login no dispositivo de teste. Substitua `<user name>` pelo nome do usuário real.
5. Efetue login no dispositivo de destino inserindo o comando a seguir em uma linha de comandos UNIX ou Linux.
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   Se você não efetuou login nesse servidor com esse nome de usuário antes, uma mensagem sobre a autenticidade do host será apresentada. Também será perguntado se você deseja continuar. Responda com **sim** para continuar.
   {:note}

6. Será solicitado para você inserir a senha, a menos que você configure as chaves SSH para acessar esse servidor antes.

## Atualizando o S.O. para se preparar para a instalação (somente RHEL)

Esta etapa é necessária para o RHEL, mas opcional para outras distribuições Linux.
{:tip}

- Execute o comando a seguir no prompt do servidor.
  ```
  yum update
  ```
  {: pre}

  Se for solicitado, confirme se o tamanho do download está correto. A atualização continua e exibe uma mensagem "Concluído" ao ser concluída.

## Obtendo o script de instalação

- Execute o comando a seguir no prompt do servidor.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## Executando o script de instalação

1. Execute o comando a seguir no prompt do servidor.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Insira seu nome de usuário e senha do portal do {{site.data.keyword.backup_notm}}.

   Para obter mais informações sobre como visualizar o nome do usuário e a senha do {{site.data.keyword.backup_notm}}, consulte [Introdução aos serviços de backup](/docs/infrastructure/Backup?topic=Backup-GettingStarted).
   {:tip}

3. Após o nome do usuário e a senha, nenhuma entrada adicional é necessária. Os prompts gravados na tela à medida que a instalação continua podem ser ignorados com segurança.

   Eles estão sendo produzidos por um subscript, que é iniciado pelo script `evault_manual.sh`. O
script `evault_manual.sh` fornece a entrada para esses prompts.
   {:note}

4. A instalação será concluída quando as mensagens a seguir aparecerem.

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## Verificando se a instalação foi bem-sucedida

1. Verifique se a mensagem "Registrado no portal" aparece na saída de instalação. A verificação pode ser feita procurando a mensagem na tela ou inspecionando a saída do comando a seguir.
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

  Os IDs do processo representados por `xxxxx` variam com cada instalação.
  {:tip}

**Etapas seguintes**

Efetue login no portal do {{site.data.keyword.backup_notm}} para configurar e gerenciar os seus agentes de backup. Para obter mais informações, consulte o [Tutorial de Introdução](/docs/infrastructure/Backup?topic=Backup-GettingStarted) e [Configurando o backup de nível de arquivo simples no Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
