---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:new_window: target="_blank"}

# Configurando BMR Tarefa de Backup no Windows

## Pré-requisito

É necessário comprar o plug-in de BMR para executar um backup de BMR. O BMR está disponível somente para
Bare Metal Servers do Windows. Nenhuma opção de BMR está disponível para o VSI.

## Ativar WebCC
**Nota**: é necessário estar conectado à rede privada do
{{site.data.keyword.BluSoftlayer_full}} para poder iniciar o WebCC.
1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor em que estão os arquivos a serem submetidos a backup. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
4. Clique em **Login do WebCC** para iniciar o cliente do WebCC em seu navegador.
  **Nota**: Se o WebCC não iniciar, pode haver um problema com a sua conexão VPN. Também
pode ser exibida uma mensagem dizendo que o formulário que você está enviando não é seguro. Essa mensagem é
esperada, portanto, continue o envio do formulário.
  
## Configure uma tarefa de backup BMR

1. Na área de janela de navegação à esquerda, clique em **Todos os agentes** para
exibir os agentes atuais do EVault
2. Clique em **Este é um novo Agente que eu gostaria de configurar**.
3. Insira um Nome e uma Descrição para a tarefa que você estiver configurando/criando.
4. Para o **Tipo de origem do backup**, selecione, no menu suspenso, o tipo de sistema de arquivos cujo backup você deseja fazer e, em seguida, clique em **Avançar**
5. O menu **Seleção de tipo de tarefa** é exibido. Marque a caixa ao lado de
**Bare Metal Restore** e clique em **Avançar** para continuar.
6. Clique em **Sim** na janela de confirmação.
7. A tela mostra que a nova tarefa está agora no Conjunto de backup. Clique em **Avançar**.
8. A tela exibe opções de criptografia e opções de backup avançadas. Normalmente esses não são necessários. 
Clique em **Avançar** para continuar com a tela **Criar um planejamento**.   
9. Na página **Criar um planejamento**, clique em **Incluir**
para planejar uma tarefa de backup baseada em tempo ou clique em **Avançar** para criar uma
tarefa manual.
  - Se você optar por criar uma tarefa manual, continue com a execução de sua nova tarefa.
  - Se você escolher planejar uma tarefa baseada em tempo, selecione os dias e o horário do dia para executar os seus backups.
  - Selecione o seu Esquema de retenção. Leia mais sobre Retenção de Esquemas [aqui](evault-backup-faq.html#how-do-the-retention-schemes-work-)
  - Depois de configurar seu planejamento de backup, clique em **Ok** para salvá-lo. A sua tarefa planejada é incluída na lista de tarefas planejadas. 
10. Selecione uma área segura para a sua tarefa de backup e clique em **Salvar mudanças**.


## Executar uma tarefa de backup de BMR
  - Se você planejou uma tarefa de backup baseada em tempo, não há etapas adicionais.  A sua tarefa será executada automaticamente conforme planejado.
  - Se você configurar uma tarefa manual (sem um planejamento baseado em tempo), selecione a linha dela na lista de tarefas e clique em **Executar backup** para executá-la. <br/> 
Assim como as tarefas baseadas em tempo, é possível escolher o **Esquema de retenção** e as
**Opções de backup avançadas**. Após concluir as suas opções de configuração, clique em **Iniciar backup** para iniciar a tarefa.
