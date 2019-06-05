---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configure BMR, bmr plug-in, bmr plugin, configuration

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurando a tarefa de backup do BMR no Windows
{: #configureBMR}

É necessário comprar o plug-in de BMR para criar um backup de BMR. O BMR está disponível somente para
Bare Metal Servers do Windows. Nenhuma opção de BMR está disponível para o VSI. Para obter mais informações, consulte [Instalando o plug-in do Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)
{:important}

## Iniciando o portal do {{site.data.keyword.backup_notm}}
{: #startWebCCBMR}

É necessário estar conectado à rede privada do {{site.data.keyword.cloud}} para poder iniciar o portal do {{site.data.keyword.backup_notm}}.
{:important}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**. <br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Clique em **Armazenamento** > **Backup** para exibir os servidores com serviços de backup.
3. Selecione o servidor no qual os arquivos a serem submetidos a backup estão localizados. Clique na seta de expansão que aponta para a direita para revelar o link do portal do {{site.data.keyword.backup_notm}}.
4. Clique em **Login do portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal em seu navegador.

   Se o portal do {{site.data.keyword.backup_notm}} não for iniciado, talvez você tenha um problema com a sua conexão de VPN. Também é possível ver uma mensagem informando que o formulário que você está enviando não é seguro. É esperado - continue enviando o formulário.
   {:tip}

## Configurando uma tarefa de backup BMR

1. Na área de janela de navegação esquerda, clique em **Todos os agentes** para exibir os Agentes atuais do {{site.data.keyword.backup_notm}}.
2. Clique em **Este é um novo Agente que eu gostaria de configurar**.
3. Insira um Nome da tarefa e uma Descrição da tarefa para a tarefa que você estiver criando.
4. Para **Tipo de origem de backup**, selecione o tipo de sistema de arquivos e, em seguida, clique em **Avançar**
5. O menu **Seleção de tipo de tarefa** é exibido. Marque a caixa próxima a **Restauração do Bare Metal** e clique em **Avançar** para continuar.
6. Clique em **Sim** na janela de confirmação.
7. A tela mostra que a nova tarefa está agora no conjunto de backup. Clique em **Avançar**.
8. A tela exibe opções de criptografia e opções de backup avançadas. Normalmente essas opções não são necessárias. Clique em **Avançar**.   
9. Na página **Criar um planejamento**, você tem duas opções.
   - Clique em **Avançar** para criar uma tarefa manual e continue a executar sua nova tarefa.
   - Clique em **Incluir** para planejar uma tarefa de backup baseada em tempo.
     1. Selecione os dias e o horário do dia para executar seus backups.
     2. Selecione o seu Esquema de retenção.

        Para obter mais informações sobre os esquemas de retenção, consulte as [Perguntas mais
frequentes](/docs/infrastructure/Backup?topic=Backup-faqs).
        {:tip}
     3. Depois de ter configurado o planejamento de backup, clique em **OK** para salvá-lo. A sua tarefa planejada é incluída na lista de tarefas planejadas.
10. Selecione uma área segura para a sua tarefa de backup e clique em **Salvar mudanças**.


## Executando uma tarefa de backup BMR

  - Se você planejou uma tarefa de backup baseada em tempo, não será necessário fazer mais nada. Sua tarefa é executada automaticamente conforme planejado.
  - Se você configurar uma tarefa manual (sem um planejamento baseado em tempo), será possível executá-la selecionando sua linha na lista de tarefas e clicando em **Executar backup**. <br/> Assim como com tarefas baseadas em tempo, é possível escolher o **Esquema de retenção** e as **Opções avançadas de backup**. Depois de ter feito suas opções de configuração, clique em **Iniciar backup** para iniciar a tarefa.
