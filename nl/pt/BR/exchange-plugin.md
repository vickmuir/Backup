---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Saiba mais sobre o plug-in do Exchange
{: #Exchangeplugin}

O plug-in do Exchange é instalado com o Windows Agent no host. Por meio do portal do {{site.data.keyword.backup_notm}}, é possível configurar tarefas, fazer backup de bancos de dados do Exchange para uma área segura remota e restaurar bancos de dados do Exchange. O plug-in integra-se à arquitetura existente.

**Recursos fornecidos**

- Capacidade para fazer backup e restaurar bancos de dados do Microsoft Exchange.

## Instalando o Plug-in
{: #installExchangePlugin}

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
11. Se o portal do {{site.data.keyword.backup_notm}} for capaz de acessar ou visualizar o banco de dados, a instalação terá sido bem-sucedida.

## Fazendo download do guia do usuário
{: #ExchangeUserGuide}

Conecte-se à rede do {{site.data.keyword.cloud}} com a {{site.data.keyword.BluVPN}} para que seja possível acessar e transferir por download o guia do usuário por meio da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ](http://downloads.service.softlayer.com/evault/Documentation/){: external}. O guia descreve como fazer backup e restaurar bancos de dados do Microsoft Exchange usando o plug-in do Exchange. O guia também descreve como compartilhar um conjunto de segurança de backup de DR. Com um conjunto de segurança de backup de DR, é possível restaurar caixas de correio, mensagens ou outros objetos específicos para um arquivo .pst usando o aplicativo Granular Restore for Microsoft Exchange.
