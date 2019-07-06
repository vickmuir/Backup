---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere, backups

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restaurando dados do vSphere
{: #VRARestore}

Quando as VMs estão protegidas no ambiente do vSphere, é possível restaurar [VMs do vSphere](#restoreVMs) e [restaurar arquivos e pastas](#restoreFFVRA) com o vSphere Recovery Agent.

## Restaurando VMs do vSphere
{: #restoreVMs}

1.	Na barra de navegação, clique em **Computadores**. Uma grade lista os computadores disponíveis.
2.	Localize o ambiente do vSphere com a VM que você deseja restaurar e expanda sua visualização clicando na linha.
3.	Clique em **Tarefas**.
4.	Localize a tarefa de backup com a VM que você deseja restaurar e clique em **Restaurar** no menu **Selecionar ação** da tarefa.
5.	Na caixa de diálogo **Escolher o que deseja restaurar**, selecione **Máquinas virtuais**.
6.	Clique em **Continuar**. O diálogo Restauração mostra o conjunto de segurança mais recente para a tarefa.
    * Para restaurar dados de outra origem, clique em uma origem (área segura) na Lista **Dispositivo de origem**.
    *	Para restaurar de um conjunto de segurança mais antigo, clique no botão **Procurar conjuntos de segurança**. No calendário que for exibido, clique na data dos conjuntos de segurança dos quais deseja restaurar.
7.	No painel **Itens a serem restaurados**, selecione cada VM que você deseja restaurar.
8.	No campo **Senha de criptografia**, digite a senha de criptografia de dados.
9.	Na lista **Armazenamento de dados de destino**, clique no armazenamento de dados para as VMs restauradas.
10.	Selecione uma das opções a seguir para restaurar VMs para o armazenamento de dados que você selecionou:
  * **Restaurar todas as Máquinas virtuais selecionadas somente para o armazenamento de dados selecionado.**
  * **Restaurar somente para o armazenamento de dados selecionado quando o armazenamento de dados original da Máquina virtual não estiver disponível.** Se a VM submetida a backup contiver múltiplos VMDKs que residiam em dois ou mais armazenamentos de dados e um ou mais dos armazenamentos de dados estiverem indisponíveis, a VM inteira será restaurada para o armazenamento de dados selecionado.

  Se você restaurar uma VM ou um modelo para um vCenter e a VM original estiver presente, a VM será restaurada como um clone da original com o nome a seguir: <nome_da_VM>-vra-restored-<Data>. A VM será restaurada como um clone se a VM original estiver ligada, desligada ou suspensa. Se a VM original estiver ligada e usar um endereço IP estático, será possível encontrar um conflito de endereço IP quando a VM restaurada e clonada for ligada.
  {:note}

13.	Na lista **Host de destino**, clique no host em que deseja registrar as VMs. A lista mostra apenas os hosts que têm acesso ao armazenamento de dados selecionado.
14.	Selecione uma das opções a seguir para registrar as VMs restauradas com os hosts que você selecionou:
  * **Registrar todas as Máquinas virtuais selecionadas somente com os hosts selecionados.**
  * **Registrar com os hosts selecionados somente quando os hosts originais de uma Máquina virtual não estiverem disponíveis.**
15.	Para ligar as VMs após a restauração, selecione **Ligar VMs após a restauração**.
16.	Em **Opções de desempenho**, mantenha a configuração padrão.
17.	Clique em **Executar restauração**.

## Restaurando arquivos e pastas
{: #restoreFFVRA}

É possível restaurar o arquivo e as pastas de uma VM do Windows protegida usando o vSphere Recovery Agent (VRA). É possível restaurar arquivos e pastas de mais de uma VM ao mesmo tempo. Não é possível restaurar arquivos e pastas de VMs do Linux com o VRA.
{:important}

Durante uma restauração de arquivos e pastas, os volumes da VM selecionada são montados como unidades na máquina em que o VRA está em execução. É possível, então, compartilhar algumas ou todas as unidades montadas para que os usuários possam copiar arquivos e pastas das unidades. Também é possível se conectar à máquina do VRA e copiar arquivos e pastas das unidades montadas.

Os arquivos e as pastas nos discos são acessíveis a qualquer pessoa no sistema VRA, incluindo usuários não administradores. Se você estiver preocupado com a segurança, proteja a máquina do Agente e impeça que os usuários efetuem login na máquina localmente.
{:tip}

1. Na barra de navegação, clique em **Computadores**. A grade lista os computadores disponíveis.
2. Localize o ambiente do vSphere com a VM que você deseja restaurar e expanda sua visualização clicando na linha.
3. Clique em **Tarefas**.
4. Localize a tarefa de backup com a VM que você deseja restaurar e clique em **Restaurar** no menu **Selecionar ação** da tarefa.
5. No diálogo **Escolher o que deseja restaurar**, selecione **Arquivos e pastas**.
6. Clique em **Continuar**. O diálogo Restauração mostra o conjunto de segurança mais recente para a tarefa.
  * Para restaurar dados de outro recurso, clique na origem na lista Dispositivo de origem (Área segura).
  * Para restaurar de um conjunto de segurança mais antigo, clique no botão Procurar conjuntos de segurança. No calendário que for exibido, clique na data do conjunto de segurança do qual deseja restaurar. À direita do calendário, clique no conjunto de segurança específico do qual deseja restaurar.
7. No painel **Itens a serem restaurados**, selecione a VM com os arquivos ou pastas que você deseja restaurar.
8. No campo **Senha de criptografia**, insira a senha de criptografia de dados.
9. No campo **Tempo inativo**, insira o número de minutos de inatividade após o qual a unidade compartilhada deve cancelar o compartilhamento automaticamente. O tempo inativo pode variar de 2 a 180 minutos.

    A unidade não cancela o compartilhamento desde que os novos dados estejam sendo copiados. Se você copiar os mesmos dados de uma unidade compartilhada mais de uma vez, o sistema poderá atingir o tempo limite, porque nenhum dado novo está sendo lido.
    {:note}

10.	Em **Opções de desempenho**, selecione Usar toda a largura da banda disponível.
11.	Clique em **Executar restauração**.
12. Os volumes restaurados da VM selecionada são mapeados como unidades na máquina em que o VRA está em execução e estão disponíveis em uma pasta Montagem de restauração.  Execute uma das etapas a seguir.
  * Copie arquivos e pastas que deseje restaurar das unidades mapeadas.
  * Compartilhe uma ou mais unidades mapeadas com outros usuários. Os usuários podem acessar o compartilhamento de UNC e copiar arquivos e pastas que desejam restaurar.
  * Compartilhe um ou mais diretórios da pasta Montagem de restauração na máquina do VRA. Os usuários podem acessar o compartilhamento de UNC e copiar arquivos e pastas que desejam restaurar.
