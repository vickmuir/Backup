---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Configurando a tarefa de backup do BMR no Windows

**Pré-requisito**

É necessário comprar o plug-in BMR para criar um backup do BMR. O BMR está disponível somente para
Bare Metal Servers do Windows. Nenhuma opção de BMR está disponível para o VSI.

## Iniciando o WebCC
**Nota**: é necessário estar conectado à rede privada do
{{site.data.keyword.BluSoftlayer_full}} para poder iniciar o WebCC.
1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor no qual os arquivos a serem submetidos a backup estão localizados. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
4. Clique em **Login do WebCC** para iniciar o cliente do WebCC em seu navegador.
**Nota**: se o WebCC não iniciar, você poderá ter um problema com a conexão VPN. Também é possível ver uma mensagem informando que o formulário que você está enviando não é seguro. É esperado - continue enviando o formulário.
  
## Configurando uma tarefa de backup de BMR

1. Na área de janela de navegação à esquerda, clique em **Todos os agentes** para exibir os Agentes de EVault atuais.
2. Clique em **Este é um novo Agente que eu gostaria de configurar**.
3. Insira um Nome e uma Descrição para a tarefa que você estiver configurando/criando.
4. Para **Tipo de origem de backup**, selecione na lista o tipo de sistema de arquivos do qual você deseja fazer backup e, em seguida, clique em **Avançar**
5. O menu **Seleção de tipo de tarefa** é exibido. Marque a caixa ao lado de
**Bare Metal Restore** e clique em **Avançar** para continuar.
6. Clique em **Sim** na janela de confirmação.
7. A tela mostra que a nova tarefa está agora no conjunto de backup. Clique em **Avançar**.
8. A tela exibe opções de criptografia e opções de backup avançadas. Normalmente essas opções não são necessárias. Clique em **Avançar**.   
9. Na página **Criar um planejamento**, você tem duas opções. 
   - Clique em **Avançar** para criar uma tarefa manual e continuar a execução de sua nova tarefa
   - Clique em **Incluir** para planejar uma tarefa de backup baseada em tempo. 
     1. Selecione os dias e o horário do dia para executar seus backups.
     2. Selecione o seu Esquema de retenção. Leia mais sobre Retenção de Esquemas [aqui](evault-backup-faq.html)
     3. Depois de ter configurado o planejamento de backup, clique em **OK** para salvá-lo. A sua tarefa planejada é incluída na lista de tarefas planejadas. 
10. Selecione uma área segura para a sua tarefa de backup e clique em **Salvar mudanças**.


## Executando uma tarefa de backup de BMR

  - Se você planejou uma tarefa de backup baseada em tempo, não será necessário fazer mais nada. Sua tarefa é executada automaticamente conforme planejado.
  - Se você configurar uma tarefa manual (sem um planejamento baseado em tempo), será possível executá-la selecionando sua linha na lista de tarefas e clicando em **Executar backup**. <br/> Assim como com tarefas baseadas em tempo, é possível escolher o **Esquema de retenção** e as **Opções avançadas de backup**. Depois de ter feito suas opções de configuração, clique em **Iniciar backup** para iniciar a tarefa.
