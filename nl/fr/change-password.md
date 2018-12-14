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

# Modification du mot de passe d'un service de sauvegarde

A chaque service {{site.data.keyword.backup_full}} est associé un mot de passe qui est utilisé pour accéder au coffre dans WebCC.

Dans de nombreux produits et services {{site.data.keyword.BluSoftlayer_full}}, la fonction de stockage du mot de passe dans le portail {{site.data.keyword.slportal}} est utilisée uniquement à des fins de suivi du mot de passe. Pour ces produits et services, les modifications qui sont apportées au mot de passe dans le portail {{site.data.keyword.slportal}} ne sont pas appliquées au produit ou au service. Ceci n'est **pas** le cas pour la sauvegarde {{site.data.keyword.backup_notm}}.

Les modifications apportées au mot de passe IBM Cloud Backup dans le portail {{site.data.keyword.slportal}} sont appliquées au service proprement dit. Lorsque vous modifiez votre mot de passe, n'oubliez pas que cela impacte directement votre service.
{:important}

## Modification du mot de passe IBM Cloud Backup

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} et cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.

   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Cliquez n'importe où sur la ligne du coffre concernée pour développer la vue.
4. Cliquez sur **Afficher** pour afficher le mot de passe en cours.
5. Entrez le nouveau mot de passe dans la zone **Mot de passe**.
6. Cliquez sur **Mettre à jour**.
