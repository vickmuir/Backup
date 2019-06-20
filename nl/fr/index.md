---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Mise à disposition de {{site.data.keyword.backup_notm}}
{: #ordering}

Vous pouvez acquérir le service {{site.data.keyword.backup_notm}} de deux manières.

- [Acquisition de sauvegardes lors de la commande d'un serveur](#purchasingwithserver).
- [Acquisition de sauvegardes sous forme de mise à niveau](#purchasingasupgrade).

Pour plus d'informations sur la tarification, voir [Stockage {{site.data.keyword.backup_notm}} ](https://www.ibm.com/cloud/backup-and-restore){: external} et [{{site.data.keyword.backup_notm}} dans IBM Cloud](https://www.ibm.com/cloud/backup/pricing){: external}.

## Acquisition d'{{site.data.keyword.backup_notm}} lors de la commande d'un serveur
{: #purchasingwithserver}

1. Connectez-vous au [catalogue IBM Cloud ](https://{DomainName}/catalog){: external}.
2. Commandez un serveur "bare metal" facturé au mois. Pour plus d'informations sur la commande de serveurs bare metal, voir [Construction de serveurs Bare Metal personnalisés](https://{DomainName}/docs/bare-metal/baremetal-provision.html){: external}.
   1. Sélectionnez l'option de facturation par quantité. Entrez les noms d'hôte et de domaine. Vous pouvez choisir n'importe quel nom d'hôte et de domaine.

      Le service {{site.data.keyword.backup_notm}} n'est pas disponible si vous commandez un serveur facturé sur une base horaire. Toutefois, vous pouvez ajouter ultérieurement le service sous forme de mise à niveau.
      {:tip}
   2. Sélectionnez l'emplacement.
   3. Sélectionnez la configuration de serveur et le type d'image de système d'exploitation. Vous pouvez également choisir plusieurs modules complémentaires.
   4. Sous la section **Disques de stockage**, cliquez sur **Modules complémentaires** et sélectionnez **{{site.data.keyword.backup_notm}}**. Choisissez l'option correspondant à vos besoins.
   5. Sous **Interface réseau**, sélectionnez la vitesse de port de liaison montante et les modules complémentaires souhaités.
3. Sur la droite, passez en revue le récapitulatif de votre commande.
4. Après avoir lu les dispositions, cochez la case **J'ai lu et j'accepte les contrats de service tiers**.
5. Cliquez sur **Mettre à disposition**. Un écran incluant votre numéro de commande de mise à disposition s'affiche. Vous pouvez imprimer cette page car il s'agit de votre reçu de commande de mise à disposition.

   Vous pouvez également sauvegarder la commande sans effectuer d'achat en cliquant sur **Enregistrer sous devis**.
   {:tip}

Plusieurs messages électroniques sont envoyés à votre administrateur (accusé de réception de la commande de mise à disposition, approbation et traitement de la commande de mise à disposition et mise à disposition terminée). Le message électronique de mise à disposition de votre commande inclut un lien vers votre page *Détails de l'unité* une fois que vous vous connectez à {{site.data.keyword.cloud_notm}}. Vous pouvez également vous connecter directement à la console {{site.data.keyword.cloud_notm}}.

### Confirmation de l'acquisition d'{{site.data.keyword.backup_notm}}
1. Sur la console [{{site.data.keyword.cloud_notm}} ](https://{DomainName}){: external}, cliquez sur l'icône de **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.
2. Cliquez sur **Unité** > **Liste des unités**.
2. Localisez le nouveau serveur vous avez commandé.
  - Si une icône en forme d'horloge est affichée en regard de l'URL, vous devez patienter avant de confirmer votre acquisition d'{{site.data.keyword.backup_notm}}. Vous pouvez actualiser la page pour voir un statut mis à jour sur votre nouveau serveur. Lorsque l'icône en forme d'horloge disparaît, vous pouvez passer aux étapes suivantes pour confirmer votre acquisition du service {{site.data.keyword.backup_notm}}.
  - Lorsque l'icône en forme d'horloge n'apparaît plus pour votre serveur, cliquez sur le lien (l'URL du serveur) afin d'accéder à la page **Détails de l'unité**.
3. Cliquez sur l'onglet **Stockage** pour afficher les informations d'{{site.data.keyword.backup_notm}}.
4. Examinez la section {{site.data.keyword.backup_notm}} et vérifiez que la taille sélectionnée lors de la procédure d'acquisition est affichée.

## Acquisition d'{{site.data.keyword.backup_notm}} sous forme de mise à niveau
{: #purchasingasupgrade}

### Sélection d'un serveur sur lequel installer {{site.data.keyword.backup_notm}}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.
2. Sélectionnez **Unités** > **Liste des unités** dans le menu principal. Recherchez le périphérique pour lequel vous voulez ajouter le service de sauvegarde.
3. Cliquez sur le nom de l'unité pour accéder à la page **Détails de l'unité**.

### Ajout (acquisition) du service {{site.data.keyword.backup_notm}}
1. Cliquez sur l'onglet **Stockage** et faites défiler l'écran jusqu'à la section {{site.data.keyword.backup_notm}}.
2. Cliquez sur le lien **Ajouter**.
3. Dans la fenêtre, sélectionnez un emplacement et choisissez une taille.
4. Sélectionnez Type de paiement et cliquez sur **Continuer**
5. Entrez un **code promo** si vous en avez un, puis cliquez sur **Recalculer**.
6. Vérifiez votre commande, puis cliquez sur le lien pour lire les dispositions.
7. Cochez la case si vous acceptez les dispositions.
7. Cliquez sur **Valider la commande**.

### Confirmation de l'acquisition d'{{site.data.keyword.backup_notm}} par mise à niveau
1. Actualisez la page **Détails de l'unité** et vérifiez que l'onglet **Stockage** est sélectionné.
2. Examinez la section {{site.data.keyword.backup_notm}} et vérifiez que la taille sélectionnée lors de la procédure d'acquisition est affichée.

   Si la taille du stockage de sauvegarde continue à afficher une capacité égale à zéro, actualisez à nouveau la page.
   {:tip}

Lorsque vous êtes prêt, procédez à l'installation de l'agent de logiciel et configurez votre planning de sauvegarde dans le portail {{site.data.keyword.backup_notm}}. Pour en savoir plus, consultez le [tutoriel d'initiation](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
