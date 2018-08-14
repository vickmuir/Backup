---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Configurando o Arquivo Simples no nível de backup no Linux

Depois de ter pedido seu serviço EVault e o agente ser instalado no servidor, é possível iniciar a criação de backups de seus dados. O artigo fornece as etapas para configurar seu agente
e o planejamento de retenção e iniciar sua primeira tarefa de backup.

## Iniciando o WebCC

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor no qual os arquivos a serem submetidos a backup estão localizados. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
3. Inicie sua conexão VPN para obter acesso à rede privada IBM.
4. Clique no link de Login do WebCC para iniciar o cliente do WebCC em seu navegador.<br/>
  **Nota**: se o WebCC não iniciar, você poderá ter um problema com a conexão VPN. Também é possível ver uma mensagem informando que o formulário que você está enviando não é seguro. É esperado - continue enviando o formulário.
  
## Configurando uma Tarefa de Backup

1. Na área de janela de navegação à esquerda, clique em **Todos os agentes** para
exibir os agentes atuais do EVault
2. Clique em **Este é um novo Agente que eu gostaria de configurar**.
3. Insira um Nome e uma Descrição para a tarefa que você estiver configurando/criando.
4. Para **Tipo de origem de backup**, selecione o tipo de sistema de arquivos do qual você deseja fazer backup no menu.
5. Clique em **Avançar** para continuar. 
6. Na área de janela **Arquivos de dados**, acesse os arquivos e diretórios que você deseja incluir em seu backup clicando nos símbolos **+** e **-** ao lado dos ícones de pasta.
7. Marque as caixas de seleção próximas aos arquivos e diretórios que deseja incluir e, em seguida, clique em **Incluir** para salvar as suas opções.
8. Filtre ainda mais suas seleções usando a tela pop-up que aparece ou clique em **OK** para usar as seleções feitas no estado em que se encontram. <br /> Depois de incluir suas opções de arquivo e de diretório, os arquivos escolhidos e os diretórios são exibidos na área de janela **Conjunto de backup** no lado direito da tela. É possível repetir as etapas de 6 a 8 para incluir mais arquivos ou para remover arquivos que você incluiu anteriormente (usando **Excluir**). Também é possível usar **Remover** para excluir qualquer
item de linha da área de janela **Conjunto de backup**. Depois que seu Conjunto de backup estiver configurado da maneira que você deseja, clique em **Avançar** para continuar.
9. Selecione o tipo de Criptografia desejado. 
  - Se você não deseja criptografar seu backup, selecione **Nenhuma**.
  - Se você deseja criptografia, selecione **AES de 256 bits** e insira uma senha
nos campos Senha e Verificar senha. Se desejar, será possível incluir uma sugestão de senha. <br/> **Nota**: essa senha é necessária para restaurar arquivos do backup. Não é possível
recuperar uma senha perdida nem restaurar um backup criptografado sem saber a senha.
10. É possível usar qualquer uma das **Opções avançadas**.
  - **Retenção**: é possível gerenciar seu uso de dados com essa opção. O período de retenção determina por quanto tempo seu backup é retido. Depois que o período de retenção é atingido, o backup é removido automaticamente. As opções integradas são Diariamente, Semanalmente ou Mensalmente.
  - **Compactação**: é possível usar essa opção para reduzir a capacidade que é usada para salvar backups. 
  - **Arquivos de backup que estão abertos para gravação**: essa opção permite que os arquivos sejam submetidos a backup, mesmo que estejam abertos em um aplicativo quando a tarefa de backup é executada.
  - **Criar arquivo de log**: para criar e gerenciar o conteúdo e a retenção de arquivos de log que são gerados durante o processo de backup com essa opção. 
  - **Fazer backup de uma única instância de todos os arquivos com link físico selecionados**. Essa opção se aplica apenas aos sistemas de estilo UNIX. Se você estiver usando links físicos para criar
múltiplos nomes de arquivos para um conteúdo, essa opção fará com que apenas uma cópia do conteúdo seja salva. Após a restauração, todos os links físicos são restaurados. Essa opção requer uma pré-varredura
dos arquivos selecionados, que pode tomar uma quantia significativa de tempo e memória.
11. Depois de ter feito sua opção de criptografia, clique em **Avançar** para continuar com a tela **Criar um planejamento**.
12. Na página Criar um planejamento, clique em **Incluir** para planejar uma tarefa de backup baseada em tempo ou clique em **Avançar** para criar uma tarefa manual.
  - Se você optar por criar uma tarefa manual, continue na Etapa 15.
  - Se você escolher planejar uma tarefa baseada em tempo, selecione os dias e o horário do dia para executar os seus backups.
  - Selecione o seu Esquema de retenção. Leia mais sobre Retenção de Esquemas [aqui](evault-backup-faq.html)
  - Clique em **Opções avançadas de planejamento** para obter mais opções de configuração. É possível selecionar **Usar o adiamento** para evitar que grandes backups sejam executados em horários de pico da rede. Quando a opção de adiamento for ativada, a tarefa de backup não fará backup de nenhum dado novo após a quantidade de tempo especificada. Ela confirma o conjunto de segurança na área segura, mesmo que alguns dados na tarefa não sejam submetidos a backup. As mudanças nos dados que foram salvos anteriormente são submetidas a backup, independentemente da quantidade de tempo especificada. <br/> Quando a tarefa é executada novamente, o agente verifica as mudanças nos dados que foram
submetidos a backup anteriormente, faz backup dessas mudanças e, em seguida, faz backup dos dados
restantes. Se uma tarefa de backup é adiada enquanto um item está sendo submetido a backup, esse backup fica incompleto, e os dados desse item não podem ser restaurados. No entanto, é possível restaurar itens que foram submetidos a backup na tarefa antes que ela seja adiada.
13. Depois de ter configurado o planejamento de backup, clique em **OK** para salvá-lo. A sua tarefa planejada é incluída na lista de tarefas planejadas. 
  - É possível repetir a etapa 12 para planejar mais backups. 
  - Para atualizar para uma tarefa de backup existente, selecione a tarefa clicando em sua linha, em seguida, clique em **Editar** e faça suas mudanças.
14. Selecione uma área segura para a sua tarefa de backup e clique em **Salvar mudanças**.
15. Execute uma tarefa de backup
  - Se você planejou uma tarefa de backup baseada em tempo, não será necessário fazer mais nada. Sua tarefa é executada automaticamente conforme planejado.
  - Se você configurar uma tarefa manual (sem um planejamento baseado em tempo), será possível executá-la agora selecionando sua linha na lista de tarefas e clicando em **Executar backup**. <br/> Assim como as tarefas baseadas em tempo, é possível escolher o Esquema de retenção e as Opções de backup
avançadas. Depois de ter feito suas opções de configuração, clique em **Iniciar backup** para iniciar a tarefa.
