---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-12"

keywords: IBM Cloud backup, EVault, Carbonite, backup, password, password reset

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Modification du mot de passe d'un service de sauvegarde
{: #changePassword}

A chaque service {{site.data.keyword.backup_full}} est associé un mot de passe qui est utilisé pour accéder au coffre dans le portail {{site.data.keyword.backup_notm}}.

Dans de nombreux produits et services {{site.data.keyword.cloud}}, la fonction de stockage du mot de passe dans la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/classic){: external} est utilisée uniquement à des fins de suivi du mot de passe. Pour ces produits et services, les modifications qui sont apportées au mot de passe dans la console {{site.data.keyword.cloud_notm}} ne sont pas appliquées au produit ou au service. Ceci n'est **pas** le cas pour la sauvegarde {{site.data.keyword.backup_notm}}.

Les modifications apportées au mot de passe {{site.data.keyword.backup_notm}} dans la console {{site.data.keyword.cloud_notm}} sont appliquées au service proprement dit. Lorsque vous modifiez votre mot de passe, n'oubliez pas que cela impacte directement votre service.
{:important}

## Modification du mot de passe

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog){: external} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.
2. Cliquez sur **Stockage** > **Sauvegarde cloud** pour afficher les serveurs avec service de sauvegarde.
3. Cliquez n'importe où sur la ligne du coffre concernée pour développer la vue.
4. Cliquez sur **Afficher** pour afficher le mot de passe en cours.
5. Entrez le nouveau mot de passe dans la zone **Mot de passe**.
6. Cliquez sur **Mettre à jour**.
