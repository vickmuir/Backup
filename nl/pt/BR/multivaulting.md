---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, multiple vaults, mulitple locations, disaster recovery

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Criação de múltiplas áreas seguras
{: #multivault}

Criação de múltiplas áreas seguras é a capacidade de um cliente conectar um servidor a mais de um local de área segura. Ela fornece redundância e tranquilidade porque os backups estarão disponíveis, mesmo se um site falhar.

**Pontos-chave**

1. Múltiplas áreas seguras podem ser gerenciadas por meio do mesmo portal do {{site.data.keyword.backup_notm}} e elas são manipuladas da mesma maneira. A única diferença é que você tem opções de área segura diferentes.
2. O licenciamento de plug-in ocorre com base na área segura. Por exemplo, se você comprou o plug-in MSSQL para uma área segura em Washington DC, ele não funcionará na área segura de Seattle.
3. A nova área segura precisa ser incluída manualmente no portal do {{site.data.keyword.backup_notm}} após cada compra.



**Localizações do {{site.data.keyword.backup_notm}} Vault Director**

A criação de múltiplas áreas seguras está disponível em todos os data centers e não há limitação
geográfica na seleção de uma área segura remota. Quando as áreas seguras estiverem configuradas corretamente, todas as áreas seguras configuradas aparecerão nas configurações de área segura.

Os backups realizados em localizações de data center remotas podem levar mais tempo do que os backups feitos no mesmo
data center no qual o servidor está localizado.
{:note}

## Incluindo uma área segura remota em uma conta

Deve-se incluir a nova área segura remota na conta antes que um novo local de backup possa ser incluído no portal do {{site.data.keyword.backup_notm}}.
{:important}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**. <br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Clique em **Dispositivos**
3. Localize e clique no link para o servidor em questão.
4. Sob **Detalhes do dispositivo**, clique em **Armazenamento**.
5. Quando a seção Armazenamento for aberta, role para baixo até
**{{site.data.keyword.backup_notm}}**e clique em **Incluir**.
6. Na janela **Pedir o {{site.data.keyword.backup_notm}}**, selecione a localização de
área segura remota clicando em sua entrada na lista suspensa.
7. Selecione o tamanho do armazenamento e, em seguida, clique em **Continuar**
8. Selecione a caixa **Eu li o Contrato de Prestação de Serviços Principal** e
clique em **Fazer pedido**.

A área segura recém-solicitada é incluída automaticamente na conta. Se não, entre em contato com vendas por ajuda.

Quando o processo de solicitação estiver concluído, acesse o **Armazenamento** > **Backup** para ver a nova área segura listada.

## Incluindo uma Área segura extra no portal do {{site.data.keyword.backup_notm}}

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**. <br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione o servidor do qual deseja poder fazer backup em múltiplas áreas seguras. Clique na seta para a direita para exibir o link do portal do {{site.data.keyword.backup_notm}}.
4. Clique no link **Login do portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal em seu navegador.

   O portal do {{site.data.keyword.backup_notm}} é acessível apenas por meio do {{site.data.keyword.BluVPN}}.
   {:tip}
5. Na área de janela de navegação esquerda, clique em **Todos os agentes**.
6. No canto superior direito, clique em **Editar** e selecione **Configurações de área segura**.
7. Na janela **Configurações de área segura**, clique em **Incluir**.
8. Na janela **Nova área segura**,
  1. No menu Perfil da área segura, escolha **Inserir configurações de área segura** para criar uma nova entrada. Não atualize a entrada existente, pois isso não funcionará.
  2. O nome da área segura não pode ser o mesmo que o nome da outra área segura. Tente incluir uma tag `-2` no final dele. <br/>

     O campo de nome da área segura tem um limite de 15 caracteres.
     {:important}
  3. O campo Endereço IP é preenchido com as informações de localização do
{{site.data.keyword.backup_notm}} Director. Por exemplo, `ev-director301.service.softlayer.com` tem o endereço IP 10.1.114.46 e está localizado em WDC.
  4. No campo de credenciais, insira o ID da conta, o nome de usuário do
{{site.data.keyword.backup_notm}} para a área segura selecionada e a senha para ela.
  5. Clique em **Salvar mudanças**.

Em alguns segundos, a nova área segura será utilizável. Se você obtiver uma falha de conexão, verifique suas configurações e tente novamente. Tenha em mente que a inclusão de uma área segura extra apresenta a você um destino extra para escolher uma tarefa. Ela não executa tarefas automaticamente com relação a ambas as áreas seguras. É necessário configurar tarefas para usar a área segura extra. Para obter mais informações, consulte o [Tutorial de introdução](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
