---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Criação de múltiplas áreas seguras

A Criação de múltiplas áreas seguras é a capacidade de um cliente/servidor se conectar a mais de um local do EVault. Ela fornece redundância e a certeza de que os backups estarão disponíveis mesmo se um site falhar. 

**Pontos de controle**

1. Múltiplos EVaults podem ser gerenciados por meio do mesmo WebCC e eles são manipulados da mesma maneira. A única diferença é que você tem opções de área segura diferentes.
2. O licenciamento de plug-in ocorre com base na área segura. Por exemplo, se você comprou o plug-in MSSQL para uma área segura em Washington DC, ele não funcionará na área segura de Seattle.
3. A nova área segura precisa ser incluída manualmente no WebCC após cada compra.

**Locais do EVault Director**

A Criação de múltiplas áreas seguras está disponível em todos os data centers e
não há limitação geográfica na seleção de uma área segura remota. Quando as áreas seguras são configuradas seguindo as etapas mencionadas neste documento, todas as áreas seguras configuradas aparecem nas configurações de área segura.

>**Nota**: o backup para locais de data center remoto pode levar mais tempo do que os backups para o mesmo data center no qual seu servidor está localizado.

## Incluindo uma área segura remota em uma conta

Deve-se incluir a nova área segura de armazenamento do EVault remota na conta antes
que um novo local de backup possa ser incluído no WebCC. 

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Clique em **Dispositivos**
3. Localize e clique no link para o servidor em questão.
4. Sob **Detalhes do dispositivo**, clique em **Armazenamento**.
5. Quando a seção Armazenamento for aberta, role para baixo até **EVault** e clique em **Incluir**.
6. Na janela **Solicitar EVault**, selecione o local da área segura remota clicando em sua entrada na lista suspensa.
7. Selecione o tamanho da quantia de armazenamento e, em seguida, clique em
**Continuar**
8. Selecione a caixa **Eu li o Contrato de Prestação de Serviços Principal** e
clique em **Fazer pedido**.

A área segura recém-solicitada é incluída automaticamente na conta. Se não, entre em contato com vendas por ajuda.
Quando o processo do pedido for concluído, acesse **Armazenamento** >
**Backup** para ver a nova área segura listada.

## Incluindo um WebCC de Segurança Adicionais

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor no qual os arquivos a serem restaurados estão localizados. Clique na seta que aponta para a direita para revelar o link do WebCC.
3. Clique no link **Login do WebCC** para iniciar o cliente WebCC em seu navegador.
   >**Nota**: o WebCC está acessível apenas por meio do {{site.data.keyword.BluVPN}}.
4. Na área de janela de navegação esquerda, clique em **Todos os agentes**.
5. No canto superior direito, clique em **Editar** e selecione **Configurações de área segura**.
6. Na janela **Configurações de área segura**, clique em **Incluir**.
7. Na janela **Nova área segura**,
  1. No menu Perfil da área segura, escolha **Inserir configurações de área segura** para criar uma nova entrada. Não atualize a entrada existente, pois isso não funcionará.
  2. O nome da área segura não pode ser o mesmo que o nome da outra área segura. Tente incluir uma tag -2 no final dele. <br/> 
     >**Nota**: esse campo tem um limite de 15 caracteres.
  3. O campo de endereço IP é preenchido com as informações de localização do EVault Director. Por exemplo, `ev-director301.service.softlayer.com` tem o endereço IP 10.1.114.46 e está localizado em WDC.
  4. No campo de credenciais, insira o ID da conta, o nome do usuário do EVault para a área segura selecionada e a senha para a área segura selecionada.
  5. Clique em **Salvar mudanças**.

Em alguns segundos, a nova área segura será utilizável. Se você obtiver uma falha de conexão, verifique suas configurações e tente novamente. Tenha em mente que a inclusão de uma área segura extra apenas apresenta um destino extra a ser escolhido para uma tarefa. Ela não executa tarefas automaticamente com relação a ambas as áreas seguras. É necessário configurar tarefas para usar a área segura extra. Consulte o [Tutorial de introdução](index.html#getting-started-with-evault-backup-services) para obter instruções.
