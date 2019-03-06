---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalando o plug-in SQL Server
{: #MSSQLplugin}

O plug-in SQL Server é instalado com o Windows Agent no host do banco de dados SQL. Por meio do portal do {{site.data.keyword.backup_notm}}, é possível configurar tarefas, fazer backup de bancos de dados SQL para uma área segura remota e restaurar bancos de dados SQL.

**Recursos fornecidos**

- É possível executar backups de banco de dados completos, backups de banco de dados completos com
logs de transações ou backup somente de logs de transação.
- É possível executar múltiplos backups ao mesmo tempo.
- É possível restaurar bancos de dados SQL para a mesma instância SQL ou para uma instância SQL
diferente,
- É possível restaurar bancos de dados com os nomes de banco de dados originais, sobrescrever bancos de dados existentes e restaurar usando a opção Sem recuperação.

Para obter mais informações, consulte a seção [Principais recursos](#main-featues).

## Pedindo o plug-in
{: #orderingSQLPlugin}

1. Efetue login no console do [{{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.<br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione a conta e clique em **Solicitar plug-ins**.
4. Selecione o **Plug-in do {{site.data.keyword.backup_notm}} - MSSQL** e clique em
**Continuar**.
5. Insira seu Código promocional, se você tiver um, e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque a caixa para indicar que você leu e aceitou os Contratos de Prestação de Serviços de Terceiros.
8. Clique em **Fazer pedido**.

## Instalando o plug-in MSSQL
{: #installSQLPlugin}

Para instalar o plug-in, execute o kit de instalação do Agente. O plug-in aparece
como uma opção na página **Configuração customizada**.

Antes de instalar o plug-in MSSQL para o servidor do Microsoft Windows, pare ambos os serviços do {{site.data.keyword.backup_notm}} em `services.msc`.
{:tip}

1. Navegue para a pasta `c:\installs\evault` e execute o arquivo .exe com o número de revisão maior.
2. Na tela de idioma, clique em **OK**.
3. Na tela de boas-vindas, clique em **Avançar**.
4. Selecione **Modificar instalação** e clique em **Avançar**.
5. Selecione **Deixar sem mudança** e clique em **Avançar**.
6. Na tela de configuração customizada, selecione cada plug-in que você comprou.
7. Selecione **Este recurso será instalado em...** e, em seguida, clique em **Avançar**.
8. Selecione **Manter meu registro atual** e clique em **Avançar**.
9. Clique em **Instalar**.
10. Quando instalado, verifique para assegurar que ambos os serviços estejam ativados e em execução.
11. Se o portal do {{site.data.keyword.backup_notm}} for capaz de visualizar e acessar o banco de dados, a instalação terá sido bem-sucedida.

## Fazendo download do guia do usuário
{: #SQLUserGuide}

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o {{site.data.keyword.BluVPN}} para que seja possível fazer download do guia do usuário da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}

## Principais recursos
{: #main-features}

- Capacidade para especificar os nomes de bancos de dados a serem incluídos e excluídos em tarefas de backup do SQL Server usando caracteres curingas (asteriscos e pontos de interrogação). Os novos bancos de dados
com nomes que correspondem aos filtros de uma tarefa de backup são incluídos ou excluídos automaticamente quando
a tarefa é executada.
- Capacidade para proteger bancos de dados secundários em AlwaysOn Availability Groups usando o plug-in Agente e SQL Server de 64 bits.
- Capacidade para compartilhar conjuntos de segurança de SQL que contêm bancos de dados de conteúdo do SharePoint 2010/2013 para uso com o aplicativo Granular Restore for Microsoft SharePoint. Depois que o conjunto de segurança é compartilhado, o aplicativo Granular Restore pode ser usado para restaurar coleções de site, websites, listas, bibliotecas, pastas, itens de lista ou documentos.
- Suporte para backup adequado para delta de bancos de dados que estão em volumes estendidos.
- Capacidade para proteger bancos de dados no modelo de recuperação integral com uma entrada única de
planejamento. Essa opção permite proteger bancos de dados e gerenciar o truncamento de logs de transações em uma
entrada única de planejamento.
- O plug-in SQL Server suporta os backups Completo, Completo com Inclusão de Logs de Transações e de Log de Transações (terminologia atualizada para alinhar-se com a terminologia do SQL Server). O aplicativo continua a suportar a função Restauração de passagem única que permite que o cliente selecione um backup de
"log de transações" no momento. O {{site.data.keyword.backup_notm}} restaura o banco de dados completo e todos
os logs de transações necessários para restaurar o banco de dados para o momento selecionado.
- Uma tarefa de backup pode conter um ou mais bancos de dados na mesma instância única do SQL
Server. Uma tarefa separada pode ser criada para fazer backup de outros bancos de dados de uma instância diferente do SQL Server, que pode ser executada simultaneamente, se desejado.
- Capacidade para restaurar bancos de dados com "Sem Recuperação" para fornecer mais opções de recuperação por meio do SQL Server Management Studio.
- A opção de restauração alternativa suporta a restauração para arquivos, o que permite que o administrador de banco de dados monte os bancos de dados por meio do SQL System Manager.
- A restauração alternativa inclui a capacidade de direcionar a restauração de um banco de dados para
outro, mesmo quando os nomes do banco de dados lógico não são correspondentes. Para objetos incompatíveis, o plug-in criará bancos de dados no local do banco de dados padrão para a instância.
- Suporte para o Transparent Data Encryption (TDE) com o SQL Server 2008 R2 (SP1) e o SQL Server
2012 de 64 bits.
- Se um host do SQL Server for perdido, o software SQL Server poderá ser instalado e o banco de dados poderá ser restaurado. (O banco de dados principal deve ser restaurado primeiro).
- Quando o backup é iniciado, ele ocorre com ou sem a execução de serviços de banco de dados.
- As restaurações são suportadas para os nomes de banco de dados originais (sobrescrevendo ou não os bancos de
dados existentes), para a restauração sobre um banco de dados existente ou para os arquivos no disco.
