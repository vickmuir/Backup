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


# Expandindo a capacidade da área segura

Os usuários do {{site.data.keyword.BluSoftlayer_full}} atuais são capazes de expandir o
tamanho da área segura até 4.000 GB. Eles não precisam criar uma duplicata ou migrar dados manualmente para um volume maior. O processo de aumento de limite não causa indisponibilidade nem falta de acesso.

## Solicitando um aumento

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.<br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os
servidores com o serviço de backup.
3. Selecione a área segura que você deseja ampliar.
4. Clique em **Ações** e selecione **Modificar o {{site.data.keyword.backup_notm}}**.
5. Na próxima tela, selecione o novo tamanho e clique em **Fazer upgrade**.

## Faturamento

O faturamento para o volume é atualizado automaticamente para incluir a diferença rateada do novo preço no ciclo de faturamento atual. Então, a nova quantia integral será faturada no próximo ciclo de faturamento.

O mesmo processo pode ser usado para reduzir o {{site.data.keyword.backup_notm}}.
{:tip}
