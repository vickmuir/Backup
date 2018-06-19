---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalando o plug-in EVault SQL Server

O plug-in do SQL Server é instalado com o Windows Agent no host do banco de dados SQL. Usando o portal
do WebCC, é possível configurar tarefas, fazer backup de bancos de dados SQL para uma área segura remota e
restaurar bancos de dados SQL.

## Recursos fornecidos

- É possível executar backups de banco de dados completos, backups de banco de dados completos com
logs de transações ou backup somente de logs de transação.
- É possível executar múltiplos backups ao mesmo tempo. 
- É possível restaurar bancos de dados SQL para a mesma instância SQL ou para uma instância SQL
diferente,
- É possível restaurar bancos de dados com os nomes de banco de dados originais, sobrescrever bancos de
dados existentes e restaurar usando a opção Nenhuma recuperação.

## Solicite o plug-in

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Clique em **Storage** > **Backup**.
3. Selecione a sua conta do EVault e clique em **Pedir plug-ins**.
4. Selecione **Plug-in do EVault - MSSQL** e clique em
**Continuar**.
5. Insira o seu Código promocional se você tiver um e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque as caixas para indicar que você leu o **Contrato de Prestação de Serviços
Principal** e aceite os **Termos de software de terceiro**. 
8. Clique em **Fazer pedido**.

## Instale o Plug-in do MSSQL

Para instalar o plug-in do SQL para Windows, execute o kit de instalação do agente. O plug-in aparece
como uma opção na página **Configuração customizada**.

**Nota**: antes de instalar o plug-in do MSSQL do EVault para seu servidor
Microsoft
Windows, pare ambos os serviços EVault em `services.msc`.  

1. Navegue para a pasta `c:\installs\evault` e execute o arquivo .exe com o número de
revisão maior.
2. Na tela de idioma, clique em **OK**.
3. Na tela de boas-vindas, clique em **Avançar**.
4. Selecione **Modificar instalação** e clique em **Avançar**.
5. Selecione **Manter inalterado** e clique em **Avançar**.
6. Na tela de configuração customizada, selecione cada plug-in que você comprou e selecione **Esse recurso será instalado em...** e, em seguida, clique em **Avançar**.
7. Selecione o botão de opções **Manter o meu registro atual** e clique em **Avançar**.
8. Clique em **Instalar**.
9. Após instalado, verifique se ambos os serviços estão ativados e em execução.
10. Se o WebCC for capaz de acessar (visualizar) os bancos de dados, então a instalação foi bem-sucedida. 

## Guia do Usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o
{{site.data.keyword.BluVPN}} para que seja possível fazer download do EVault Agent for Microsoft
Windows v8.0 - SQL Server Plug-in Guide.pdf na
[Documentação do EVault transferível
por download](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Perguntas Mais Frequentes

### O que o VSS (Serviço de Cópia de Sombra de Volume) faz?

A versão atual do plug-in do SQL Server usa o VSS (Serviço de Cópia de Sombra de Volume)
para executar backups. Usando o VSS, o plug-in do SQL Server faz backup efetivamente de bancos
de dados SQL, de bancos de dados SQL que abrangem volumes, permite que os backups sejam executados enquanto os
aplicativos continuam gravando em um volume e fornece consistência de dados dentro e entre os bancos de dados. 
O VSS permite que múltiplos backups sejam executados ao mesmo tempo.

### Quais são os principais recursos do plug-in do SQL?

- Capacidade de especificar os nomes de bancos de dados a serem incluídos e excluídos nas tarefas de
backup do SQL Server usando caracteres curinga (asteriscos e pontos de interrogação). Os novos bancos de dados
com nomes que correspondem aos filtros de uma tarefa de backup são incluídos ou excluídos automaticamente quando
a tarefa é executada. 
- Capacidade para proteger bancos de dados secundários em Grupos de disponibilidade AlwaysOn usando o
agente de 64 bits e o plug-in do SQL Server.
- Capacidade para compartilhar conjuntos de segurança SQL contendo bancos de dados de conteúdo do
SharePoint 2010/2013 para uso com o aplicativo Granular Restore for Microsoft SharePoint. Quando um conjunto
de segurança é compartilhado, o aplicativo Granular Restore pode ser usado para restaurar coleções de site,
websites, listas, bibliotecas, pastas, itens de lista ou documentos.
- Suporte para um backup Delta fácil de bancos de dados localizados em volumes ampliados.
Capacidade para proteger bancos de dados no modelo de recuperação integral com uma entrada única de
planejamento. Essa opção permite proteger bancos de dados e gerenciar o truncamento de logs de transações em uma
entrada única de planejamento.
- O plug-in do SQL Server suporta backups completos, completos com inclusão de logs de
transações e de log de transação (a terminologia foi atualizada para alinhar-se à terminologia do SQL Server). 
O EVault continuará a suportar a funcionalidade Restauração de passagem única, que permite que o cliente
selecione um backup de “log de transações” de momento. O EVault restaurará bancos de dados completos e
todos os logs de transações necessários para restaurar o banco de dados para o momento selecionado.
- Uma tarefa de backup pode conter um ou mais bancos de dados na mesma instância única do SQL
Server. Uma tarefa separada pode ser criada para fazer backup de outros bancos de dados por meio de uma
instância diferente do SQL Server que pode ser executada simultaneamente, se desejado.
- Capacidade de restaurar bancos de dados com a opção "Nenhuma recuperação" para fornecer opções de
recuperação adicionais por meio do SQL Server Management Studio.
- Uma opção de restauração alternativa suporta a restauração para arquivos, que permite que o
administrador de banco de dados monte os bancos de dados por meio do SQL System Manager.
- A restauração alternativa inclui a capacidade de direcionar a restauração de um banco de dados para
outro, mesmo quando os nomes do banco de dados lógico não são correspondentes. Para objetos incompatíveis, o
plug-in criará bancos de dados no local do banco de dados padrão para a instância.
- Suporte para o Transparent Data Encryption (TDE) com o SQL Server 2008 R2 (SP1) e o SQL Server
2012 de 64 bits.
- Se um host do SQL Server for completamente perdido, o software SQL Server poderá ser instalado e o
banco de dados poderá ser completamente restaurado. (o banco de dados principal deve ser restaurado primeiro).
- Quando o backup é iniciado, ele ocorre com ou sem os serviços de banco de dados em
execução.
- As restaurações são suportadas para nomes de bancos de dados originais (sobrescrevendo ou não os
bancos de dados existentes), para um banco de dados existente ou para arquivos no disco.

