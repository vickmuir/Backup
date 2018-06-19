---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-16"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restaurar a partir de um Backup

Este artigo fornece as etapas necessárias para executar uma restauração de arquivo usando o EVault. Para restaurar uma imagem do sistema, siga as instruções de [Recuperação bare-metal do Windows](restoring-evault-bmr-system-volume-image.html).

## Iniciar WebCC

**Nota**: lembre-se de iniciar sua conexão do {{site.data.keyword.BluVPN}}
para obter acesso à rede privada do {{site.data.keyword.BluSoftlayer_full}} ou o link do WebCC não
funcionará.

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor em que estão os arquivos a serem restaurados. Clique na seta para revelar o
link do WebCC.
3. Clique em **WebCC** para iniciar o cliente do WebCC em seu navegador. 

## Execute a restauração

1. Na área de janela de navegação à esquerda, clique em **Todos os agentes**
2. Clique no agente para exibir as tarefas.
3. Clique na tarefa que contém o backup desejado.
4. Clique em **Executar restauração**
5. Selecione uma origem de restauração.
6. Selecione **Restaurar por meio de um único conjunto de segurança** ou
**Restaurar por meio do conjunto de segurança inserido na caixa de texto abaixo**. Ambas as
opções têm o mesmo efeito.
7. Selecione uma versão de backup ou insira o número do conjunto de segurança (o número do conjunto de
segurança é o primeiro número na seleção suspensa)
8. Digite a senha de criptografia.
9. Clique em **Avançar** para continuar.
10. Marque as caixas de seleção próximas aos arquivos e diretórios que deseja incluir e, em seguida, clique em **Incluir** para salvar as suas opções.
11. É possível filtrar ainda mais as suas seleções usando a tela pop-up que aparece ou clicar em **OK** para usar as seleções feitas no estado em que se encontram. <br/>
Depois de ter incluído suas opções de arquivo e de diretório, os arquivos não podem mais ser selecionados na
área de janela **Arquivos de dados**. Eles são exibidos na
área de janela **Conjunto de backup** à direita a mão lado da tela. É possível repetir a
etapa 101 para incluir mais arquivos ou remover arquivos que você já incluiu (usando
**Excluir**). Também é possível usar **Remover** para excluir qualquer
item de linha da área de janela **Conjunto de backup**. Quando seu conjunto de backup estiver
configurado conforme desejado, clique em **Avançar** para continuar.
12. Deixe as configurações padrão na próxima área de janela ou customize a restauração como preferir
e, em seguida, clique em **Executar restauração**. 
13. Os arquivos estão totalmente restaurados quando o Status exibe **Restauração
concluída** na tela **Detalhes do processo**.
