---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Instalando EVault Backup Client para VMware

A instalação do EVault Backup Client em um servidor VMware pode ser feita por meio de uma série de
comandos no shell ou no terminal dentro do servidor ESX de destino. Este procedimento descreve as etapas
necessárias para instalar o EVault Backup Client em seu servidor VMware:

Para instalar o agente, faça download e copie o pacote `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz`
para o ESX Server de destino usando o comando a seguir:

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**Nota**: deve-se executar as seguintes etapas localmente no ESX Server de destino.

1. Extraia os arquivos do pacote. Para isso, use este comando (em que “PACKAGENAME” pode ser
“Agent-VMware-ESX-Server-6.71”): `tar xvfz PACKAGENAME.tar.gz`
2. Acesse o diretório no qual você extraiu o pacote.
3. Execute o script de instalação:
    `# ./install.sh`

    **Nota**: o script de instalação solicitará interativamente informações de
configuração, como o registro da web (endereço, número da porta e autenticação) e o nome do arquivo de log.
     
    - Insira o nome do usuário do WebCC para esse servidor.
    - Insira a senha do WebCC para esse servidor.
     
4. Insira o **Nome do usuário do EVault Backup** como a entrada para o prompt que
solicita o nome do usuário do WebCC. 
5. Insira a **Senha do EVault Backup** como a entrada para o prompt que solicita a
senha do WebCC.
6. Quando a instalação for concluída, uma mensagem de conclusão será exibida e o daemon do agente
estará em execução.


### Outras Notas de Instalação:
O Install.log estará no diretório de instalação se a instalação for bem-sucedida.
Por exemplo: `/opt/BUAgent/Install.log`

Se a instalação falhar e retroceder, o log de instalação estará no `<Installation Failure directory>`.
Se ela falhar e não retroceder, o log de instalação estará no `<Installation Kit directory>`.

Para obter mais informações, faça download do [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}. 
Certifique-se de estar conectado ao {{site.data.keyword.BluVPN}} para visualizar esse link.
