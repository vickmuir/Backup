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


# Extension de la capacité de coffre

Les utilisateurs {{site.data.keyword.BluSoftlayer_full}} actuels peuvent étendre la taille de leur coffre jusqu'à 4 000 Go. Ils n'ont pas besoin de créer un double ou de faire migrer manuellement leurs données vers un volume plus grand. Le processus d'extension de la limite n'engendre aucune indisponibilité ou problème d'accès au coffre.

## Commande d'une extension

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window}, puis cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez le coffre que vous souhaitez étendre.
4. Cliquez sur **Actions** et sélectionnez **Modifier {{site.data.keyword.backup_notm}}**.
5. Sur l'écran suivant, sélectionnez la nouvelle taille et cliquez sur **Mettre à niveau**.

## Facturation

La facturation du volume est automatiquement mise à jour pour ajouter la différence au prorata du nouveau prix au cycle de facturation en cours. Ensuite, le nouveau montant total est facturé au cours du cycle de facturation suivant.

La même procédure peut être utilisée pour réduire la taille de votre {{site.data.keyword.backup_notm}}.
{:tip}
