---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalando o Plug-in do Exchange

O plug-in do Exchange é instalado com o Windows Agent no host. Por meio do portal do {{site.data.keyword.backup_notm}}, é possível configurar tarefas, fazer backup de bancos de dados do Exchange para uma área segura remota e restaurar bancos de dados do Exchange. O plug-in integra-se à arquitetura existente.

**Recursos fornecidos**

- Capacidade para fazer backup e restaurar bancos de dados do Microsoft Exchange.

## Solicitando o plug-in

1. Efetue login no [console do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/){:new_window} e clique no ícone **Menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.<br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione a sua conta e clique em **Solicitar plug-ins**.
4. Selecione o **Plug-in do {{site.data.keyword.backup_notm}} - Exchange** e clique em
**Continuar**.
5. Insira seu Código promocional, se você tiver um, e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque a caixa para indicar que você leu e aceitou os Contratos de Prestação de Serviços de Terceiros.
8. Clique em **Fazer pedido**.

## Instalando o Plug-in do Exchange

O plug-in do Exchange é instalado durante a instalação do Windows Agent de 64 bits. O plug-in pode ser instalado ao mesmo tempo que o Agente ou posteriormente, executando novamente a instalação com a seleção **Modificar**.

Antes de instalar o plug-in para o servidor do Microsoft Windows, pare ambos os serviços do
{{site.data.keyword.backup_notm}} em `services.msc`.
{:tip}

1. Navegue para a pasta `c:\installs\{{site.data.keyword.backup_notm}}` e execute o arquivo .exe
com o número de revisão mais alto.
2. Na tela de idioma, clique em **OK**
3. Na tela de boas-vindas, clique em **Avançar**
4. Selecione **Modificar instalação** e clique em **Avançar**.
5. Selecione **Deixar sem mudança** e clique em **Avançar**.
6. Na tela de configuração customizada, selecione cada plug-in que você comprou.
7. Selecione **Este recurso será instalado em...** e, em seguida, clique em **Avançar**.
8. Selecione **Manter meu registro atual** e clique em **Avançar**.
9. Clique em **Instalar**.
10. Quando instalado, verifique para assegurar que ambos os serviços estejam ativados e em execução.
11. Se o portal do {{site.data.keyword.backup_notm}} for capaz de acessar/visualizar o banco de dados, a instalação foi bem-sucedida.

## Fazendo download do guia do usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o {{site.data.keyword.BluVPN}} para que seja possível acessar e fazer download do guia do usuário da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} O guia descreve como fazer backup e restaurar bancos de dados do Microsoft Exchange usando o plug-in do Exchange. O guia também descreve como compartilhar um conjunto de segurança de backup DR. Com um conjunto de segurança de backup DR, é possível restaurar caixas de correio, mensagens ou outros objetos específicos para um arquivo .pst usando o aplicativo Granular Restore for Microsoft Exchange.
