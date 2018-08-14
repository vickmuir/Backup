---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-27"

---
{:new_window: target="_blank"}

# Instalando o Plug-in do EVault Exchange

O plug-in do Exchange é instalado com o Windows Agent no host. Por meio do portal do WebCC, é possível configurar tarefas, fazer backup dos bancos de dados Oracle para uma área segura remota e restaurar bancos de dados Oracle. O plug-in do Oracle se integra à arquitetura existente.

**Recursos fornecidos**

- Capacidade para fazer backup e restaurar bancos de dados do Microsoft Exchange.

## Solicitando o plug-in

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup**.
3. Selecione sua conta do EVault e clique em **Pedir plug-ins**.
4. Selecione **Plug-in do EVault - Exchange** e clique em **Continuar**.
5. Insira seu Código promocional, se você tiver um, e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque a caixa para indicar que você leu e aceitou os Contratos de Prestação de Serviços de Terceiros. 
8. Clique em **Fazer pedido**.

## Instalando o Plug-in do Exchange

O plug-in do Exchange é instalado durante a instalação do Windows Agent de 64 bits. O plug-in pode ser instalado ao mesmo tempo que o Agente ou posteriormente, executando novamente a instalação com a seleção **Modificar**.

**Nota**: antes de instalar o plug-in para seu servidor Microsoft Windows, pare ambos os serviços do EVault em `services.msc`.  

1. Navegue para a pasta `c:\installs\evault` e execute o arquivo .exe com o
número de revisão maior.
2. Na tela de idioma, clique em **OK**
3. Na tela de boas-vindas, clique em **Avançar**
4. Selecione **Modificar instalação** e clique em **Avançar**.
5. Selecione **Deixar sem mudança** e clique em **Avançar**.
6. Na tela de configuração customizada, selecione cada plug-in que você comprou. 
7. Selecione **Este recurso será instalado em...** e, em seguida, clique em **Avançar**.
8. Selecione **Manter meu registro atual** e clique em **Avançar**.
9. Clique em **Instalar**.
10. Quando instalado, verifique para assegurar que ambos os serviços estejam ativados e em execução.
11. Se o WebCC puder acessar/visualizar o banco de dados, a instalação foi bem-sucedida. 

## Fazendo download do guia do usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o {{site.data.keyword.BluVPN}} para que seja possível fazer download do EVault Agent v8.0 for Microsoft Windows (64 bits) - Guia do plug-in Exchange.pdf em
[Documentação do EVault transferível por download](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. O guia descreve como fazer backup e restaurar bancos de dados do Microsoft Exchange usando o plug-in do Exchange. O guia também descreve como compartilhar um conjunto de segurança de backup DR. Com um conjunto de segurança de backup DR, é possível restaurar caixas de correio, mensagens ou outros objetos específicos para um arquivo .pst usando o aplicativo Granular Restore for Microsoft Exchange.

