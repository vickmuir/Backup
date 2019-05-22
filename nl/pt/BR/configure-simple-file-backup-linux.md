---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configuration, linux

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurando o backup em nível de arquivo simples no Linux
{: #configureLinuxBackup}

Depois de ter solicitado o {{site.data.keyword.backup_full}} e o agente estiver instalado no
servidor, será possível iniciar a criação de backups dos dados. O artigo fornece as etapas para configurar seu agente
e o planejamento de retenção e iniciar sua primeira tarefa de backup.

## Iniciando o portal do {{site.data.keyword.backup_notm}}
{: #startWebCCconfigLin}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**. <br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
2. Selecione o servidor no qual os arquivos a serem submetidos a backup estão localizados. Clique na seta de expansão que aponta para a direita para revelar o link do portal do {{site.data.keyword.backup_notm}}.
3. Inicie sua conexão VPN para obter acesso à rede privada IBM.
4. Clique no link Login do portal do {{site.data.keyword.backup_notm}} para iniciar o cliente do portal em seu navegador.<br/>

  Se o portal do {{site.data.keyword.backup_notm}} não for iniciado, talvez você tenha um problema com a sua conexão de VPN. Também é possível ver uma mensagem informando que o formulário que você está enviando não é seguro. É esperado - continue enviando o formulário.
  {:tip}

## Configurando uma tarefa de backup

1. Na área de janela de navegação, clique em **Todos os agentes** para exibir os Agentes atuais do {{site.data.keyword.backup_notm}}
2. Clique em **Este é um novo Agente que eu gostaria de configurar**.
3. Insira um Nome da tarefa e uma Descrição da tarefa para a tarefa que você estiver criando.
4. Para **Tipo de origem de backup**, selecione o tipo de sistema de arquivos que você deseja submeter a backup.
5. Clique em **Avançar** para continuar.
6. Na área de janela de arquivos de dados, acesse os arquivos e os diretórios que você deseja incluir no backup clicando nos símbolos **+** e **-** próximos aos ícones de pasta.
7. Selecione as caixas de seleção próximas aos arquivos e diretórios que você deseja incluir, em seguida, clique em **Incluir** para salvar suas opções.
8. Filtre ainda mais suas seleções usando a tela pop-up que aparece ou clique em **OK** para usar as seleções feitas no estado em que se encontram. Depois de incluir suas opções de arquivo e diretório, os arquivos e os diretórios escolhidos serão exibidos na área de janela do conjunto de backup no lado direito da tela. Clique em **Avançar** para continuar.

   É possível repetir as etapas de 6 a 8 para incluir mais arquivos ou para remover arquivos que você incluiu anteriormente (usando **Excluir**). Também é possível usar **Remover** para excluir qualquer item de linha da área de janela do conjunto de backup. Depois que seu conjunto de backup estiver configurado da maneira desejada,
   {:tip}
9. Selecione o tipo de Criptografia desejado.
  - Se você não deseja criptografar seu backup, selecione **Nenhuma**.
  - Se você deseja criptografia, selecione **AES de 256 bits** e insira uma senha
nos campos Senha e Verificar senha. Também é possível incluir uma Sugestão de senha.

    Essa senha é necessária para restaurar os arquivos por meio do backup. Sem a senha, não é possível restaurar um backup criptografado e não há nenhuma maneira de recuperar uma senha perdida.
    {:important}
10. É possível usar qualquer uma das **Opções avançadas**.
  - **Retenção**: é possível gerenciar seu uso de dados com essa opção. O período de retenção determina por quanto tempo seu backup é retido. Depois que o período de retenção é atingido, o backup é removido automaticamente. As opções integradas são Diariamente, Semanalmente ou Mensalmente.
  - **Compactação**: é possível usar essa opção para reduzir a capacidade que é usada para salvar backups.
  - **Arquivos de backup que estão abertos para gravação**: essa opção permite que os arquivos sejam submetidos a backup, mesmo que estejam abertos em um aplicativo quando a tarefa de backup é executada.
  - **Criar arquivo de log**: para criar e gerenciar o conteúdo e a retenção de arquivos de log que são gerados durante o processo de backup com essa opção.
  - **Fazer backup de uma única instância de todos os arquivos com link físico selecionados**. Essa opção se aplica apenas aos sistemas de estilo UNIX. Se você estiver usando links físicos para criar
múltiplos nomes de arquivos para um conteúdo, essa opção fará com que apenas uma cópia do conteúdo seja salva. Após a restauração, todos os links físicos são restaurados. Essa opção requer uma pré-varredura
dos arquivos selecionados, que pode tomar uma quantia significativa de tempo e memória.
11. Depois de ter feito a opção de criptografia, clique em **Avançar** para continuar
na tela **Criar um planejamento**.
12. Na página Criar um planejamento, clique em **Incluir** para planejar uma tarefa de backup baseada em tempo ou clique em **Avançar** para criar uma tarefa manual.
  - Se você optar por criar uma tarefa manual, continue na Etapa 15.
  - Se você escolher planejar uma tarefa baseada em tempo, selecione os dias e o horário do dia para executar os seus backups.
  - Selecione o seu Esquema de retenção. Para obter mais informações sobre os esquemas de retenção, consulte as [Perguntas mais
frequentes](/docs/infrastructure/Backup?topic=Backup-faqs).
  - Clique em **Opções avançadas de planejamento** para obter mais opções de configuração. É possível selecionar **Usar o adiamento** para evitar que grandes backups sejam executados em horários de pico da rede.

    Quando a opção de adiamento for ativada, a tarefa de backup não fará backup de nenhum dado novo após a quantidade de tempo especificada. Ela confirmará o conjunto de segurança para a área segura, mesmo se alguns dados na tarefa não forem submetidos a backup. As mudanças nos dados que foram salvos anteriormente são submetidas a backup, independentemente da quantidade de tempo especificada. <br/> Quando a tarefa é executada novamente, o agente verifica as mudanças nos dados que foram
submetidos a backup anteriormente, faz backup dessas mudanças e, em seguida, faz backup dos dados
restantes. Se uma tarefa de backup é adiada enquanto um item está sendo submetido a backup, esse backup fica incompleto, e os dados desse item não podem ser restaurados. No entanto, é possível restaurar itens que foram submetidos a backup na tarefa antes que ela seja adiada.
    {:note}
13. Depois de ter configurado o planejamento de backup, clique em **OK** para salvá-lo. A sua tarefa planejada é incluída na lista de tarefas planejadas.
  - É possível repetir a etapa 12 para planejar mais backups.
  - Para atualizar para uma tarefa de backup existente, selecione a tarefa clicando em sua linha, em seguida, clique em **Editar** e faça suas mudanças.
14. Selecione uma área segura para a sua tarefa de backup e clique em **Salvar mudanças**.
15. Execute uma tarefa de backup
  - Se você planejou uma tarefa de backup baseada em tempo, não será necessário fazer mais nada. Sua tarefa é executada automaticamente conforme planejado.
  - Se você configurar uma tarefa manual (sem um planejamento baseado em tempo), será possível executá-la agora selecionando sua linha na lista de tarefas e clicando em **Executar backup**. Assim como as tarefas baseadas em tempo, é possível escolher o **Esquema de retenção** e as
**Opções de backup avançadas**. Depois de ter feito suas opções de configuração, clique em **Iniciar backup** para iniciar a tarefa.
