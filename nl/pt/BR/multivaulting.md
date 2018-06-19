---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Multivaulting

A Criação de múltiplas áreas seguras é a capacidade de um cliente/servidor de conectar-se a mais de um local do EVault. Ele
fornece redundância e a tranquilidade de que os backups estarão disponíveis, mesmo se um site falhar. 

## Pontos

1. Múltiplos EVaults podem ser gerenciados por meio do mesmo WebCC e são manipulados da mesma
maneira. A única diferença é que você tem opções de área segura diferentes.
2. O licenciamento de plug-in ocorre em uma base por área segura, por exemplo, se você licenciou um
EVault para o plug-in do MSSQL em Washington DC, ele não funcionará na área segura de Seattle.
3. O novo EVault precisa ser incluído manualmente no WebCC após cada pedido.

## Incluindo uma área segura remota em uma conta

Deve-se incluir a nova área segura de armazenamento do EVault remota na conta antes
que um novo local de backup possa ser incluído no WebCC. 

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Clique em **Dispositivos**
3. Localize e clique no link para o servidor em questão.
4. Em **Detalhes do Dispositivo** , clique em **Storage**
5. Quando a seção Armazenamento for aberta, role para abaixo até **EVault** e clique
em **Incluir**
6. Na caixa de diálogo **Solicitar o EVault** que se abre, selecione o
local da área segura remota clicando na lista suspensa.
7. Selecione o tamanho da quantia de armazenamento e, em seguida, clique em
**Continuar**
8. Selecione a caixa **Eu li o Contrato de Prestação de Serviços Principal** e
clique em **Fazer pedido**.

A área segura recém-solicitada é incluída automaticamente na conta. Se não, entre em contato com vendas por ajuda.
Quando o processo do pedido for concluído, acesse **Armazenamento** >
**Backup** para ver a nova área segura listada.

## Incluindo um WebCC de Segurança Adicionais

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione o servidor em que estão os arquivos a serem restaurados. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
3. Clique no link de Login do WebCC para iniciar o cliente do WebCC em seu navegador. <br/>**Nota**: WebCC é acessível apenas por meio do {{site.data.keyword.BluVPN}}.
4. Na área de janela de navegação esquerda, clique em **Todos os agentes**.
5. No canto superior direito, clique em **Editar** e selecione
**Configurações de área segura**.
6. Na janela **Configurações de área segura", clique em **Incluir**.
7. No campo **Nova Área Segura** caixa de diálogo:
  1. Na lista suspensa Perfil de área segura, escolha **Inserir configurações de
área segura** para criar uma nova entrada. Não atualize a entrada existente, pois isso não vai
funcionar.
  2. O nome da área segura não deve ser igual ao nome da outra área segura. É recomendado incluir
uma tag -2 no término dele. <br/> **Nota**: esse campo tem um limite de 15 caracteres.
  3. O campo de endereço IP será preenchido com informações de localização do evdirector. Por exemplo,
ev-director301.service.softlayer.com tem o endereço IP 10.1.114.46 e está localizado em WDC. Consulte a parte
inferior da página para obter outros locais e endereços do EVault Director.
  4. No campo de credenciais, a conta será o ID da conta do cliente, o nome do usuário será o nome de
usuário do EVault para a área segura selecionada e a senha será a senha para a área segura selecionada.
  5. Clique em **Salvar Mudanças**.

Em alguns segundos, a nova área segura se tornará utilizável. Se ocorrer uma falha ao conectar-se, verifique
suas configurações e tente novamente. Lembre-se de que a inclusão de uma área segura extra
apresenta somente um destino adicional a ser escolhido para uma tarefa e não executa automaticamente as tarefas
com relação a ambas as áreas seguras. As tarefas precisam ser configuradas para fazer uso da área
segura adicional. Consulte o [Tutorial de Introdução](index.html#getting-started-with-evault-backup-services) para obter instruções.

## Locais EVault Director

A Criação de múltiplas áreas seguras está disponível em todos os data centers e
não há limitação geográfica na seleção de uma área segura remota. Quando as áreas seguras são configuradas
seguindo as etapas mencionadas neste documento, todas as áreas seguras configuradas aparecem nas configurações
de área segura.

**Nota**: o backup para locais de data center remotos pode demorar mais do
que os backups para o mesmo data center no qual seu servidor está localizado.

