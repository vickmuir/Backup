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

# Instalando o plug-in do Bare Metal Restore

A BMR é uma solução de recuperação de desastre para o Microsoft Windows. É possível usar o BMR para restaurar seu servidor de um estado bare metal após a ocorrência de um desastre, como uma falha de sistema operacional ou de hardware. Com a BMR, é possível restaurar rapidamente a imagem do sistema de uma localização segura e
protegida gerenciada pelo {{site.data.keyword.BluSoftlayer_full}}.

A BMR é um produto apenas para Microsoft Windows em servidores físicos. Ele
não está disponível para servidores virtuais. Distribuições de Bare Metal Restores para Linux não
são suportadas. A BMR é suportada apenas pelo Backup Agent 8.30 ou versões anteriores. (30 de junho de 2018).
{:important}

**Recursos fornecidos**

- Restaure seu sistema para um momento selecionado.
- Restaure seu sistema por meio de backups de imagem ou baseados em arquivo.
- Restaure seu sistema por meio de backups armazenados no {{site.data.keyword.backup_notm}}.
- Uma transação de recuperação apta para ativação que pode ser usada para restaurar seus dados sem um sistema inicializável.

## Pedindo o plug-in

1. Efetue login no console do [{{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**. <br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione a sua conta e clique em **Solicitar plug-ins**.
4. Selecione o **Plug-in do {{site.data.keyword.backup_notm}} - BMR (restauração bare-metal)** e clique em **Continuar**.
5. Insira seu Código promocional, se você tiver um, e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque a caixa para indicar que você leu e aceitou os Contratos de Prestação de Serviços de Terceiros.
8. Clique em **Fazer pedido**.

## Fazendo download do guia do usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o {{site.data.keyword.BluVPN}} para que seja possível acessar e fazer download do guia do usuário da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
