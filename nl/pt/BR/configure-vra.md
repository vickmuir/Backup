---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurando as tarefas de backup do VRA
{: #ConfigureVRA}

Após o ambiente do VMware vSphere ser incluído no Portal do {{site.data.keyword.backup_notm}}, é possível criar uma tarefa de backup que especifique quais máquinas virtuais (VMs) devem passar por backup e onde salvar os dados de backup. Para fazer backup dos dados, é possível executar a tarefa de backup manualmente ou planejar a execução da tarefa de backup.

Deve-se definir as configurações da área segura e as informações do vCenter antes de poder incluir uma tarefa de backup.
{:important}

## Iniciando o portal do {{site.data.keyword.backup_notm}}
{: #startWebCCVRA}

É necessário estar conectado à rede privada do {{site.data.keyword.BluSoftlayer_full}} para poder iniciar o portal do {{site.data.keyword.backup_notm}}.
{:important}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.<br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os servidores com serviços de backup.
3. Selecione o servidor no qual os arquivos a serem submetidos a backup estão localizados. Clique na seta de expansão que aponta para a direita para revelar o link do portal do {{site.data.keyword.backup_notm}}.
4. Clique em **Login do portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal em seu navegador.

   Se o portal do {{site.data.keyword.backup_notm}} não for iniciado, talvez você tenha um problema com a sua conexão de VPN. Também é possível ver uma mensagem informando que o formulário que você está enviando não é seguro. É esperado - continue enviando o formulário.
   {:tip}

## Incluindo uma tarefa de backup do vSphere

1. Na navegação, clique em **Computadores**. A página de computadores mostra os computadores e os ambientes registrados.
2. Clique em **Tarefas**.
3. No menu Selecionar atividade de tarefa, clique em **Criar nova tarefa do VMware vCenter**.
4. Especifique as informações a seguir.
   * No campo **Nome**, digite um nome para a tarefa de backup.
   * No campo **Descrição**, digite opcionalmente uma descrição para a tarefa de backup.
   * Na lista **Destino**, selecione a área segura em que deseja salvar os dados de backup.
   * Nos campos **Senha** e **Confirmar senha**, digite uma senha de criptografia. Também é possível digitar uma sugestão de senha no campo Sugestão de senha.
   Uma área segura será exibida na lista somente se estiver designada ao usuário ou se o usuário a incluiu nas Configurações de área segura do computador.<br/>
   Para novas tarefas de backup, o método de criptografia é AES de 256 bits. As tarefas existentes podem ter outros métodos de criptografia.
   {:note}

5.	No campo **Incluir no backup**, execute uma ou mais das etapas a seguir até que o campo Conjunto de backup mostre as VMs que você deseja incluir na tarefa de backup:

   * Para incluir VMs específicas na tarefa de backup, selecione cada VM e, em seguida, clique em **Incluir**.
   * Para excluir VMs específicas da tarefa de backup, selecione cada VM e, em seguida, clique em **Excluir**.
   * Para incluir VMs na tarefa de backup por nome, marque a caixa Máquinas virtuais e, em seguida, clique em **Incluir**.
   * Para remover um registro de inclusão ou exclusão da caixa Conjunto de backup, clique em **Excluir** ao lado do registro.

6. Clique em **Aplicar agora** para consolidar e simplificar registros na caixa Conjunto de backup, se as mudanças precisarem ser aplicadas.
7. Clique em **Criar tarefa**.

## Configurando um Planejamento

Após a tarefa de backup ser criada, será possível incluir um ou mais planejamentos para executar a tarefa automaticamente.

1. Quando você clica em **Criar tarefa**, a janela Planejar é exibida e fornece uma opção para configurar um planejamento customizado para a tarefa de backup.

   Por padrão, a retenção Diária é selecionada para a tarefa. O planejamento de Retenção e Tarefa pode ser mudado nessa janela, e vários esquemas de Retenção também podem ser designados à tarefa de backup.
   {:note}
2. Clique em **Salvar** para salvar o novo planejamento. A nova tarefa é mostrada na guia Computadores na seção Tarefas. O status do Último backup mostra que a tarefa nunca foi executada. A tarefa de backup planejada é executada automaticamente no horário planejado.

## Executando uma tarefa planejada

As tarefas de backup planejadas também podem ser executadas imediatamente.

1. Clique em **Selecionar ação** e selecione **Executar tarefa**. A janela Executar tarefa é exibida e fornece informações sobre a Área segura de destino e o esquema de Retenção que estão designados à tarefa.

   Se vários esquemas de retenção e áreas seguras forem designados à tarefa, essas opções poderão ser mudadas na janela Executar tarefa clicando nas opções de menu Destino e esquema de retenção.
   {:note}
2. Clique em **Iniciar tarefa de backup** para executar a tarefa de backup imediatamente. A janela de progresso mostra o status da tarefa de backup e, quando a tarefa é concluída, o status da tarefa muda de "Nunca executada" para "Concluída".

Para ver o status da última tarefa de backup que foi executada, clique na guia Tarefas. Todos os logs da tarefa podem ser acessados no menu de ação. Clique em **Ação** e selecione **Histórico/logs**.
{:tip}

Para obter mais informações sobre a restauração de VMs ou de arquivos e pastas, consulte [Restaurando dados do vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore).
