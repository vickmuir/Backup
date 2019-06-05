---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalando o cliente de backup no Windows
{: #InstallinWindows}

A instalação do cliente do {{site.data.keyword.backup_full}} no Windows é concluída por meio de
uma série de interações no servidor que está designado para o serviço do {{site.data.keyword.backup_notm}}.

Para obter mais informações sobre os backups para servidores Windows 2016, consulte [Configurando o {{site.data.keyword.backup_notm}} no Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016).
{:tip}

## Efetuando login no servidor de dispositivo de destino
{: #logintargetWin}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**. <br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Selecione **Dispositivos** > **Lista de dispositivos** no menu principal para ver a lista de servidores disponíveis.
3. Localize o dispositivo para o qual você comprou o serviço do {{site.data.keyword.backup_notm}} e anote
seu endereço IP público.
4. Clique na seta que aponta para a direita para expandir e mostrar mais informações sobre o dispositivo, incluindo o nome do usuário e a senha. Se a senha não for exibida, clicar em **Mostrar senha** a revelará.
5. Efetue login no dispositivo de destino usando a Conexão de Área de Trabalho Remota.

## Fazendo download do cliente de backup

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do arquivo executável para o cliente do {{site.data.keyword.backup_notm}}. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Dê um clique duplo no arquivo transferido por download.
3. Clique em  ** Executar **.


## Instalando e registrando o agente de backup

1. Insira o endereço de rede: <br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Insira o nome do usuário no campo **Nome do usuário**.
3. Insira a senha no campo **Senha**.
6. Clique em **Avançar**
7. Clique em **Instalar** para concluir a instalação.

## Configurando agentes de backup

Efetue login no portal do {{site.data.keyword.backup_notm}} para configurar e gerenciar os seus agentes de backup. Para obter mais informações, consulte o [Tutorial de introdução](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
