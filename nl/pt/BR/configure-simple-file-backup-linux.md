---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurando o Arquivo Simples no nível de backup no Linux

Após ter solicitado seu serviço EVault e instalado o agente no servidor, é possível
iniciar a criação de backups de seus dados. O artigo fornece as etapas para configurar seu agente
e o planejamento de retenção e iniciar sua primeira tarefa de backup.

## Ativar WebCC

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor em que estão os arquivos a serem submetidos a backup. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
3. Inicie sua conexão VPN para obter acesso à rede privada IBM.
4. Clique no link de Login do WebCC para iniciar o cliente do WebCC em seu navegador.<br/>
  **Nota**: Se o WebCC não iniciar, pode haver um problema com a sua conexão VPN. Também
pode ser exibida uma mensagem dizendo que o formulário que você está enviando não é seguro. Essa mensagem é
esperada, portanto, continue o envio do formulário.
  
## Configurar uma Tarefa de Backup

1. Na área de janela de navegação à esquerda, clique em **Todos os agentes** para
exibir os agentes atuais do EVault
2. Clique em **Este é um novo Agente que eu gostaria de configurar**.
3. Insira um Nome e uma Descrição para a tarefa que você estiver configurando/criando.
4. Para o **Tipo de origem do backup**, selecione, no menu suspenso, o tipo de sistema de arquivos
cujo backup você deseja fazer.
5. Clique em **Avançar** para continuar. 
6. Na área de janela **Arquivos de dados**, navegue até os arquivos e
diretórios que você deseja incluir no seu backup clicando nos símbolos **+** e
**-** ao lado dos ícones de pasta.
7. Marque as caixas de seleção próximas aos arquivos e diretórios que deseja incluir e, em seguida, clique em **Incluir** para salvar as suas opções.
8. É possível filtrar ainda mais as suas seleções usando a tela pop-up que aparece ou clicar em **OK** para usar as seleções feitas no estado em que se encontram. <br /> 
Depois de ter incluído suas opções de arquivo e diretório, seus arquivos e diretórios escolhidos são exibidos
na área de janela **Conjunto de backup** à direita da tela. É possível repetir
as etapas de 6 a 8 para incluir mais arquivos ou para remover arquivos já incluídos (usando o botão
**Excluir**). Também é possível usar o botão **Remover** para
excluir qualquer item de linha da área de janela **Conjunto de backup**. Após configurar
seu Conjunto de backup conforme desejado, clique em **Avançar** para
continuar.
9. Selecione o tipo de criptografia que você quer. 
  - Se você não deseja criptografar seu backup, selecione **Nenhuma**.   
  - Se você deseja criptografia, selecione **AES de 256 bits** e insira uma senha
nos campos Senha e Verificar senha. Se desejar, será possível incluir uma sugestão de senha. <br/> 
**Nota**: essa senha é necessária para restaurar arquivos do backup. Não é possível
recuperar uma senha perdida nem restaurar um backup criptografado sem saber a senha.   
10. Se você deseja usar qualquer uma das **Opções avançadas**, aqui está uma
explicação de cada opção:
  - A **Retenção** ajuda a gerenciar o uso de seus dados. O período de retenção
determina por quanto tempo seu backup será retido. Após o período de retenção ter sido atingido, o backup
será removido automaticamente. As opções integradas são Diariamente, Semanalmente ou Mensalmente.
  - A **Compactação** é usada para reduzir a quantia de capacidade utilizada para
salvar backups.
Os arquivos de backup abertos para a opção de gravação permitirão que os arquivos sejam submetidos a backup, mesmo
se eles estiverem abertos por um aplicativo quando a tarefa de backup for executada.
  - **Criar arquivo de log** permite criar e gerenciar o conteúdo e a retenção de
arquivos de log gerados durante o processo de backup. 
  - **Fazer backup de uma instância única de todos os arquivos com link físico selecionados**. 
Essa opção se aplica apenas aos sistemas de estilo Unix. Se você estiver usando links físicos para criar
múltiplos nomes de arquivos para um conteúdo, essa opção fará com que apenas uma cópia do conteúdo seja salva. 
Após a restauração, todos os links físicos são restaurados. Essa opção requer uma pré-varredura
dos arquivos selecionados, que pode tomar uma quantia significativa de tempo e memória.
11. Depois de fazer a sua escolha de criptografia, clique em **Avançar** para
continuar com a tela **Criar um planejamento**.   
12. Na página Criar um planejamento, clique em **Incluir** para planejar uma tarefa
de backup baseada em tempo ou clique em **Avançar** para criar uma tarefa manual.
  - Se você optar por criar uma tarefa manual, continue na Etapa 15.
  - Se você escolher planejar uma tarefa baseada em tempo, selecione os dias e o horário do dia para executar os seus backups.
  - Selecione o seu Esquema de retenção. Leia mais sobre Retenção de Esquemas [aqui](evault-backup-faq.html#how-do-the-retention-schemes-work-)
  - Clique em **Opções de planejamento avançadas** para obter opções de configuração
adicionais, se desejado. É possível selecionar **Usar adiamento* para evitar que backups grandes sejam
executados em horários de pico de rede. Quando o adiamento é ativado, a tarefa de backup não faz backup de
nenhum dado novo após a quantia de tempo especificada e confirma o conjunto de segurança para a área
segura, mesmo caso alguns dados na tarefa não tenham sido submetidos a backup. As mudanças nos dados que foram
submetidos a backup anteriormente serão submetidas a backup, independentemente da quantia de tempo
especificada. <br/> Quando a tarefa é executada novamente, o agente verifica as mudanças nos dados que foram
submetidos a backup anteriormente, faz backup dessas mudanças e, em seguida, faz backup dos dados
restantes.  Se uma tarefa de backup é adiada enquanto um item (por exemplo, arquivo, banco de dados, volume,
vSphere VMDK ou VM Hyper-V) está sendo submetido a backup, o backup para esse item se torna incompleto e os
dados desse item não podem ser restaurados. No entanto, é possível restaurar os itens que foram completamente
submetidos a backup na tarefa antes de a tarefa ter sido adiada.
13. Depois de configurar seu planejamento de backup, clique em **Ok** para salvá-lo. A sua tarefa planejada é incluída na lista de tarefas planejadas. 
  - É possível repetir a etapa 12 para planejar backups adicionais. 
  - Para fazer mudanças em uma tarefa de backup existente, selecione a tarefa clicando em sua linha, e
em seguida, clique em **Editar** e faça suas mudanças.
14. Selecione uma área segura para a sua tarefa de backup e clique em **Salvar mudanças**.
15. Execute uma tarefa de backup
  - Se você planejou uma tarefa de backup baseada em tempo, não há etapas adicionais.  A sua tarefa será executada automaticamente conforme planejado.
  - Se você configurar uma tarefa manual (sem um planejamento baseado em tempo), selecione a linha dela na lista de tarefas e clique em **Executar backup** para executá-la. <br/> 
Assim como as tarefas baseadas em tempo, é possível escolher o Esquema de retenção e as Opções de backup
avançadas. Após concluir as suas opções de configuração, clique em **Iniciar backup** para iniciar a tarefa.
