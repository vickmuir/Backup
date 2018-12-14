---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restaurando a partir de um Backup

Use essas etapas para concluir uma restauração de arquivo com o {{site.data.keyword.backup_full}}. Para restaurar uma imagem do sistema, siga as instruções de [Recuperação bare-metal do Windows](restore-bmr-system-volume-image.html).

## Iniciando o WebCC

Lembre-se de iniciar a conexão do {{site.data.keyword.BluVPN}} para obter acesso à rede privada
do {{site.data.keyword.BluSoftlayer_full}}. O link do WebCC não funciona de outra forma.
{:important}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e
clique no ícone **Menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.

   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione o servidor no qual os arquivos a serem restaurados estão localizados. Clique na seta para revelar o
link do WebCC.
4. Clique em **WebCC** para iniciar o cliente do WebCC em seu navegador.

## Restaurando seus dados

1. Na área de janela navegacional à esquerda, clique em **Todos os agentes**.
2. Clique no agente para exibir as tarefas.
3. Clique na Tarefa que contém o backup desejado.
4. Clique em **Executar restauração**.
5. Selecione uma origem de restauração.
6. Selecione uma versão de backup.
7. Insira a senha de criptografia.
8. Clique em **Avançar** para continuar.
9. Selecione as caixas de seleção próximas aos arquivos e diretórios que você deseja incluir, em seguida, clique em **Incluir** para salvar suas opções.
10. Filtre ainda mais suas seleções usando a janela que aparece ou clique em **OK** para usar as seleções feitas no estado em que se encontram.
Depois de ter incluído suas opções de arquivo e de diretório, os arquivos não podem mais ser selecionados na área de janela **Arquivos de dados**. Eles são exibidos na área de janela **Conjunto de backup** à direita.

   É possível repetir a etapa 10 para incluir mais arquivos ou para remover arquivos que você incluiu
anteriormente (usando **Excluir**). Também é possível usar **Remover** para excluir qualquer
item de linha da área de janela **Conjunto de backup**.
   {:tip}
11. Quando seu conjunto de backup estiver configurado conforme desejado, clique em **Avançar** para continuar.
12. Deixe as configurações padrão na próxima área de janela ou customize a restauração como preferir
e, em seguida, clique em **Executar restauração**.
13. Os arquivos são restaurados quando o Status exibe **Restauração concluída** na tela **Detalhes do processo**.
