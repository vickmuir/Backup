---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restaurando de um backup
{: #simplerestore}

Use essas etapas para concluir uma restauração de arquivo com o {{site.data.keyword.backup_full}}. Para restaurar uma imagem do sistema, siga as instruções de [Recuperação bare-metal do Windows](https://cloud.ibm.com/docs/infrastructure/Backup?topic=Backup-restoreBMR#restoreBMR).

## Iniciando o portal do {{site.data.keyword.backup_notm}}
{: #startWebCCsimple}

Lembre-se de iniciar a conexão do {{site.data.keyword.BluVPN}} para obter acesso à rede privada
do {{site.data.keyword.cloud}}. Caso contrário, o link do portal do {{site.data.keyword.backup_notm}} não funcionará.
{:important}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione o servidor no qual os arquivos a serem restaurados estão localizados. Clique na seta para exibir o link do portal do {{site.data.keyword.backup_notm}}.
4. Clique em **Portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal do {{site.data.keyword.backup_notm}} em seu navegador.

## Restaurando seus dados

1. Na área de janela navegacional à esquerda, clique em **Todos os agentes**.
2. Clique no agente para exibir as tarefas.
3. Clique na Tarefa que contém os dados que você deseja.
4. Clique em **Executar restauração**.
5. Selecione a origem da restauração.
6. Selecione a versão de backup.
7. Insira a senha de criptografia.
8. Clique em **Avançar** para continuar.
9. Marque as caixas de seleção próximas ao arquivos e diretórios que você deseja incluir. Em seguida, clique em **Incluir** para salvar suas opções.
10. Filtre ainda mais suas seleções usando a janela que aparece ou clique em **OK** para usar as seleções feitas no estado em que se encontram.
Depois de incluir suas opções de arquivo e diretório, os arquivos não poderão mais ser selecionados na área de janela de arquivos de dados. Eles serão exibidos na área de janela do conjunto de backup à direita.

   É possível repetir a etapa 10 para incluir mais arquivos ou para remover arquivos que você incluiu
anteriormente (usando **Excluir**). Também é possível usar **Remover** para excluir qualquer
item de linha da área de janela **Conjunto de backup**.
   {:tip}

11. Quando seu conjunto de backup estiver configurado conforme desejado, clique em **Avançar** para continuar.
12. Deixe as configurações padrão na próxima área de janela ou customize a restauração de acordo com sua preferência. Em seguida, clique em **Executar restauração**.
13. Os arquivos são restaurados quando o Status exibe **Restauração concluída** na tela **Detalhes do processo**.
