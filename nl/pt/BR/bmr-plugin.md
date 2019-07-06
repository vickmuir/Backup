---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Saiba mais sobre o plug-in do Bare Metal Restore
{: #BMRplugin}

O BMR é uma solução de recuperação de desastre. É possível usar o BMR para restaurar seu servidor de um estado bare metal após a ocorrência de um desastre, como uma falha de sistema operacional ou de hardware. Com a BMR, é possível restaurar rapidamente a imagem do sistema de uma localização segura e
protegida gerenciada pelo {{site.data.keyword.cloud}}.

A BMR é um produto apenas para Microsoft Windows em servidores físicos. Ele
não está disponível para servidores virtuais. Distribuições de Bare Metal Restores para Linux não
são suportadas. A BMR é suportada apenas pelo Backup Agent 8.30 ou versões anteriores. (30 de junho de 2018).
{:important}

## Recursos fornecidos
{: #BMRcapabilities}

- Restaure seu sistema para um momento selecionado.
- Restaure seu sistema por meio de backups de imagem ou baseados em arquivo.
- Restaure seu sistema por meio de backups armazenados no {{site.data.keyword.backup_notm}}.
- Uma transação de recuperação apta para ativação que pode ser usada para restaurar seus dados sem um sistema inicializável.

## Instalando o plug-in do BMR
{: #installingBMR}

O plug-in é instalado durante a instalação do Windows Agent. O plug-in pode ser instalado ao mesmo tempo que o Agente ou posteriormente, executando novamente a instalação com a seleção **Modificar**.

## Configurando a tarefa de backup do BMR
{: #configBMRplugin}

Para obter mais informações, consulte [Configurando tarefas de backup do BMR](/docs/infrastructure/Backup?topic=Backup-configureBMR).

## Restaurando uma imagem de volume do sistema BMR
{: #restoringBMimage}
Para obter mais informações, consulte [Restaurando uma imagem de volume do sistema BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

## Fazendo download do guia do usuário
{: #BMRUserGuide}

Conecte-se à rede do {{site.data.keyword.cloud}} com a {{site.data.keyword.BluVPN}} para que seja possível acessar e fazer download do guia do usuário por meio da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ](http://downloads.service.softlayer.com/evault/Documentation/){: external}
