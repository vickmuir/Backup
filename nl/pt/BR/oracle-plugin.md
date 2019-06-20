---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, oracle, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Saiba mais sobre o plug-in do Oracle
{: #Oracleplugin}

O plug-in do Oracle é um complemento e é instalado com o Agente do Windows ou com o Agente Linux no host do banco de dados Oracle. Por meio do portal do {{site.data.keyword.backup_notm}}, é possível configurar tarefas, fazer backup de bancos de dados Oracle para uma área segura remota e restaurar bancos de dados Oracle. O plug-in do Oracle se integra à arquitetura existente.

## Recursos fornecidos
{: #Oraclecapabilities}

- Suporte para backup e recuperação de banco de dados Oracle.
- O plug-in do Oracle fornece backups não RMAN e baseados em ARCHIVELOG de
instâncias de banco de dados on-line inteiras. Todos os espaços de tabela não temporários e arquivos de parâmetro de instância são submetidos a backup automaticamente. A Oracle Corporation recomenda que os backups ocorram
em períodos de baixa atividade do banco de dados.
- Os bancos de dados completos e parciais são restaurados por meio de mecanismos de recuperação
normais do Oracle gerenciados pelo usuário.

## Limitations
{: #Oraclelimitations}
- Somente bancos de dados locais de instância única e baseados em disco são submetidos a backup.
- Clusters de Banco de Dados não são submetidos a backup.
- Dispositivos brutos não são submetidos a backup.
- Bancos de dados remotos não são submetidos a backup.
- O banco de dados deve ser executado no modo ARCHIVELOG e o usuário sob o qual o backup está
configurado deve ter privilégios SYSDBA.
- As senhas do banco de dados são criptografadas para melhor segurança sobre os métodos baseados em
script.

## Instalando o plug-in para Windows
{: #installOracleWin}

O plug-in do Oracle para Windows é instalado com o Windows Agent de 32 ou 64 bits. Para instalar o plug-in, execute o kit de instalação do Agente. O plug-in aparece
como uma opção na página **Configuração customizada**. Para obter mais informações, consulte [Instalando o {{site.data.keyword.backup_notm}} Client no Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)

Antes de instalar o plug-in, pare ambos os serviços do {{site.data.keyword.backup_notm}} no `services.msc`.
{:tip}

1. Navegue para a pasta `c:\installs\evault` e execute o arquivo .exe com o número de revisão maior.
2. Na tela de idioma, clique em **OK**
3. Na tela de boas-vindas, clique em **Avançar**
4. Selecione **Modificar instalação** e clique em **Avançar**.
5. Selecione **Deixar sem mudança** e clique em **Avançar**.
6. Na tela de configuração customizada, selecione cada plug-in que você comprou e selecione **Este recurso será instalado em...** e, em seguida, clique em **Avançar**.
7. Selecione **Manter meu registro atual** e clique em **Avançar**.
8. Clique em **Instalar**.
9. Quando a instalação estiver concluída, verifique para assegurar que ambos os serviços estejam ativados e em execução.
10. Se o portal do {{site.data.keyword.backup_notm}} for capaz de acessar ou visualizar o banco de dados, a instalação terá sido bem-sucedida.

## Instalando o plug-in para Linux
{: #installOracleLin}

O plug-in do Oracle é um complemento para o Agente Linux e é instalado com o agente no host do banco de dados. O aplicativo Linux Agent deve ser instalado antes que a instalação do plug-in ocorra. O agente está disponível como um aplicativo de 32 bits e um aplicativo de 64 bits. Para obter mais informações, consulte [Instalando o {{site.data.keyword.backup_notm}} Client no Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux).

O kit de instalação do plug-in do Oracle está disponível em um arquivo tar.gz.

1. No host, faça o download do pacote de instalação.
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. Extraia os arquivos do pacote.
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. Acesse a pasta.
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. Execute o script de instalação.
   ```
   # ./install.sh
   ```
   {: pre}

5. Siga as instruções de instalação exibidas na tela.

O plug-in do Oracle executa um backup de banco de dados completamente "inconsistente" que requer que o banco de dados seja executado no modo ARCHIVELOG. O DBA precisa assegurar que o banco de dados esteja no modo ARCHIVELOG antes de os backups serem iniciados. Para obter mais informações, consulte o Guia do usuário.
{:important}


## Fazendo download do guia do usuário
{: #OracleUserGuide}

Conecte-se à rede do {{site.data.keyword.cloud}} com a {{site.data.keyword.BluVPN}} para que seja possível fazer download dos guias do usuário por meio da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ](http://downloads.service.softlayer.com/evault/Documentation/){: external}
