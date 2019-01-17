---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Initiation aux services {{site.data.keyword.backup_notm}}

Les sauvegardes permettent de stocker en toute sécurité vos données hors de votre appareil et de les protéger si celui-ci venait à être perdu. {{site.data.keyword.backup_full}} est un système de sauvegarde automatisé basé sur un agent qui est géré via l'utilitaire de gestion de portail {{site.data.keyword.backup_notm}} reposant sur un navigateur. {{site.data.keyword.backup_notm}} fournit aux utilisateurs une méthode de sauvegarde des données entre les serveurs d'un ou de plusieurs centres de données sur le réseau {{site.data.keyword.BluSoftlayer_full}}. Les administrateurs peuvent faire en sorte que des sauvegardes soient effectuées tous les jours, toutes les semaines ou définir des sauvegardes personnalisées qui ciblent des systèmes complets, des répertoires spécifiques ou même des fichiers individuels. Des plug-ins supplémentaires permettent la compatibilité avec des logiciels tels que Microsoft Exchange et Microsoft SQL, ainsi qu'avec d'autres types de logiciels tiers. Ils permettent également aux utilisateurs d'effectuer une restauration physique, en cas de besoin.

## Commande de {{site.data.keyword.backup_notm}}

Vous pouvez acquérir le service {{site.data.keyword.backup_notm}} de deux manières.

- [Acquisition d'{{site.data.keyword.backup_notm}} lors de la commande d'un serveur](#purchasing-ibm-cloud-backup-when-you-order-a-server).
- [Acquisition d'{{site.data.keyword.backup_notm}} sous forme de mise à niveau](#purchasing-ibm-cloud-backup-as-an-upgrade).

Pour plus d'informations sur la tarification, voir [Stockage {{site.data.keyword.backup_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/cloud/backup-and-restore){:new_window} et [{{site.data.keyword.backup_notm}} on IBM Cloud ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Acquisition d'{{site.data.keyword.backup_notm}} lors de la commande d'un serveur

1. Connectez-vous au [catalogue IBM Cloud ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/catalog/){:new_window} ou au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}
2. Commandez un serveur "bare metal" facturé au mois. Pour plus d'informations sur la commande de serveurs bare metal, voir [Construction de serveurs Bare Metal personnalisés](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}.
   1. Sélectionnez l'option de facturation par quantité. Entrez les noms d'hôte et de domaine. Vous pouvez choisir n'importe quel nom d'hôte et de domaine.

      Le service {{site.data.keyword.backup_notm}} n'est pas disponible si vous commandez un serveur facturé sur une base horaire. Toutefois, vous pouvez ajouter ultérieurement le service sous forme de mise à niveau.
      {:tip}
   2. Sélectionnez l'emplacement.
   3. Sélectionnez la configuration de serveur et le type d'image de système d'exploitation. Vous pouvez également choisir plusieurs modules complémentaires.
   4. Sous la section **Disques de stockage**, cliquez sur **Modules complémentaires** et sélectionnez **Sauvegarde {{site.data.keyword.backup_notm}}**. Choisissez l'option correspondant à vos besoins.
   5. Sous **Interface réseau**, sélectionnez la vitesse de port de liaison montante et les modules complémentaires souhaités.
3. Sur la droite, passez en revue le récapitulatif de votre commande.
4. Après avoir lu les dispositions, cochez la case **J'ai lu et j'accepte les contrats de service tiers**.
5. Cliquez sur **Mettre à disposition**. Un écran incluant votre numéro de commande de mise à disposition s'affiche. Vous pouvez imprimer cette page car il s'agit de votre reçu de commande de mise à disposition.

   Vous pouvez également sauvegarder la commande sans effectuer d'achat en cliquant sur **Enregistrer sous devis**.
   {:tip}

Plusieurs messages électroniques sont envoyés à votre administrateur (accusé de réception de la commande de mise à disposition, approbation et traitement de la commande de mise à disposition et mise à disposition terminée). Le message électronique de mise à disposition de votre commande inclut un lien vers votre page *Détails de l'unité* une fois que vous vous connectez à {{site.data.keyword.cloud_notm}}. Vous pouvez également vous connecter directement au portail {{site.data.keyword.slportal}}.

#### Confirmation de l'acquisition d'{{site.data.keyword.backup_notm}}
1. Dans la [console {{site.data.keyword.cloud_notm}}![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/){:new_window}, cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.</br>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Unité** > **Liste des unités**.
2. Localisez le nouveau serveur vous avez commandé.
  - Si une icône en forme d'horloge est affichée en regard de l'URL, vous devez patienter avant de confirmer votre acquisition d'{{site.data.keyword.backup_notm}}. Vous pouvez actualiser la page pour voir un statut mis à jour sur votre nouveau serveur. Lorsque l'icône en forme d'horloge disparaît, vous pouvez passer aux étapes suivantes pour confirmer votre acquisition du service {{site.data.keyword.backup_notm}}.
  - Lorsque l'icône en forme d'horloge n'apparaît plus pour votre serveur, cliquez sur le lien (l'URL du serveur) afin d'accéder à la page **Détails de l'unité**.
3. Cliquez sur l'onglet **Stockage** pour afficher les informations d'{{site.data.keyword.backup_notm}}.
4. Examinez la section {{site.data.keyword.backup_notm}} et vérifiez que la taille sélectionnée lors de la procédure d'acquisition est affichée.

### Acquisition d'{{site.data.keyword.backup_notm}} sous forme de mise à niveau

#### Sélection d'un serveur sur lequel installer {{site.data.keyword.backup_notm}}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}){:new_window}, puis cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.</br>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Sélectionnez **Unités** > **Liste des unités** dans le menu principal. Recherchez le périphérique pour lequel vous désirez ajouter le service de sauvegarde {{site.data.keyword.cloud_notm}}.
3. Cliquez sur le nom de l'unité pour accéder à la page **Détails de l'unité**.

#### Ajout (acquisition) du service {{site.data.keyword.backup_notm}}
1. Cliquez sur l'onglet **Stockage** et faites défiler l'écran jusqu'à la section {{site.data.keyword.backup_notm}}.
2. Cliquez sur le lien **Ajouter**.
3. Dans la fenêtre, sélectionnez un emplacement et choisissez une taille.
4. Sélectionnez Type de paiement et cliquez sur **Continuer**
5. Entrez un **code promo** si vous en avez un, puis cliquez sur **Recalculer**.
6. Vérifiez votre commande, puis cliquez sur le lien pour lire les dispositions.
7. Cochez la case si vous acceptez les dispositions.
7. Cliquez sur **Valider la commande**.

#### Confirmation de l'acquisition d'{{site.data.keyword.backup_notm}} par mise à niveau
1. Actualisez la page **Détails de l'unité** et vérifiez que l'onglet **Stockage** est sélectionné.
2. Examinez la section {{site.data.keyword.backup_notm}} et vérifiez que la taille sélectionnée lors de la procédure d'acquisition est affichée.

   Si la taille du stockage de sauvegarde continue à afficher une capacité égale à zéro, actualisez à nouveau la page.
   {:tip}

## Accès et examen des détails du stockage du service de stockage {{site.data.keyword.backup_notm}}

Vous pouvez à tout moment accéder aux détails du stockage de votre service {{site.data.keyword.backup_notm}} dans la [console {{site.data.keyword.cloud_notm}} ](https://{DomainName}/catalog/){:new_window} et le portail {{site.data.keyword.slportal}}. Les détails que vous pouvez consulter comprennent le mot de passe, l'adresse de stockage et l'utilisation qui sont associés au service {{site.data.keyword.backup_notm}} sélectionné.

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window}, puis cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.</br>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** et sélectionnez **Sauvegarde** dans la liste.
2. Cliquez n'importe où sur la ligne du coffre dont vous souhaitez examiner les informations de stockage. Dans cette vue, le mot de passe n'est pas visible. Passez à l'étape suivante pour examiner le mot de passe associé à votre service {{site.data.keyword.backup_notm}}.
3. Cochez la case **Afficher** en regard de la zone **Mot de passe** pour examiner le mot de passe du service {{site.data.keyword.backup_notm}} sélectionné.

Dans de nombreux produits et services {{site.data.keyword.BluSoftlayer_full}}, la fonction de stockage du mot de passe dans le portail {{site.data.keyword.slportal}} est utilisée uniquement à des fins de stockage ou de suivi du mot de passe. Pour ces offres, les modifications qui sont apportées au mot de passe dans le portail {{site.data.keyword.slportal}} ne sont pas appliquées au produit ou au service.

Ce n'est _pas_ le cas pour {{site.data.keyword.backup_notm}}. Les modifications apportées au mot de passe {{site.data.keyword.backup_notm}} dans le portail {{site.data.keyword.slportal}} sont appliquées au service proprement dit. Lorsque vous modifiez votre mot de passe, n'oubliez pas que cela impacte directement votre service. Pour réinitialiser votre mot de passe, suivez la procédure décrite dans [Modification d'un mot de passe {{site.data.keyword.backup_notm}} dans le portail {{site.data.keyword.slportal}}](change-password.html).
{:important}

## Installation de l'agent {{site.data.keyword.backup_notm}}

L'agent {{site.data.keyword.backup_notm}} est pris en charge sur les systèmes d'exploitation suivants :

**Windows**
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Suivez les instructions correspondant à votre système d'exploitation.
- [Installation du client de sauvegarde sous Linux](install-backup-client-linux.html)
- [Installation du client de sauvegarde sous Windows](install-backup-client-windows.html)
- [Installation du client de sauvegarde sous Windows 2016](install-backup-client-windows2016.html)

## Accès au portail {{site.data.keyword.backup_notm}} (anciennement WebCC)

Le portail {{site.data.keyword.backup_notm}} est utilisé pour interagir avec un service {{site.data.keyword.backup_notm}} offert par {{site.data.keyword.BluSoftlayer_full}}. Le portail {{site.data.keyword.backup_notm}} est un client reposant sur un navigateur qui s'exécute sur le réseau privé {{site.data.keyword.BluSoftlayer_full}} et permet de contrôler totalement un service {{site.data.keyword.backup_notm}}, notamment pour la configuration et les restaurations.

1. Accédez au réseau privé via VPN.

   Le portail {{site.data.keyword.backup_notm}} n'est pas accessible via le réseau public. Une connexion VPN doit d'abord être établie.
   {:important}
2. Accédez à l'écran de stockage de sauvegarde sur le portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
3. Cliquez n'importe où sur la ligne du service {{site.data.keyword.backup_notm}} concernée pour développer la vue.
4. Cliquez sur **Connexion au portail {{site.data.keyword.backup_notm}}** pour lancer le client de portail {{site.data.keyword.backup_notm}} dans votre navigateur.

## Configuration de l'agent de sauvegarde et du planning de sauvegarde

Une fois que vous avez commandé votre {{site.data.keyword.backup_notm}} et que l'agent a été installé sur le serveur, vous pouvez commencer à créer des sauvegardes de vos données. Procédez comme suit pour configurer votre agent, le planning de conservation des données et lancer votre premier travail de sauvegarde.

1. Connectez-vous à WebCC.
2. Cliquez sur **Tous les agents**> **Agents non configurés**.
3. Cliquez sur le lien **Il s'agit d'un nouvel agent que je désire configurer**. Suivez cette procédure en spécifiant les informations suivantes :
   1. Configuration de l'agent - fournissez la description, puis cliquez sur **suivant**.
   2. Sélection d'un type de travail - entrez le nom du travail, sa description, le type de source de la sauvegarde, puis cliquez sur **suivant**.
   3. Sélection - sélectionnez des répertoires et cliquez sur **Inclure...**
   4. Options - fournissez des mots de passe
   5. Planning - cliquez sur **Ajouter** pour créer un planning, puis cliquez sur **Suivant**.
   6. Sélectionnez le coffre par défaut, puis cliquez sur **OK**.
   7. Cliquez sur **Enregistrer**.
4. Créez un planning de conservation.
   1. Sélectionnez **Editer** > **Paramètres de l'agent**.
   2. Cliquez sur **Ajouter**.
   3. Renseignez les informations de conservation de vos données.
   4. Cliquez sur **OK**.
   5. Cliquez sur **Enregistrer**.

      Pour plus d'informations sur les schémas de conservation, voir la [Foire aux questions](faqs.html).
      {:tip}
5. Lancez l'agent et déclenchez une sauvegarde.
   1. Cliquez sur **Tous les agents**, puis sélectionnez celui que vous avez configuré.
   2. Cliquez sur **Exécuter une sauvegarde**.
   3. Confirmez la destination de sauvegarde et sélectionnez un schéma de conservation des données.
   4. Cliquez sur **Lancer la sauvegarde**. Vous pouvez afficher les détails de la sauvegarde pendant l'exécution du processus.
   5. Une fois la sauvegarde terminée, cliquez sur **Fermer**.

Pour plus d'informations sur les sauvegardes de niveau fichier sous Linux, voir [Configuration d'une sauvegarde simple au niveau fichier sous Linux](configure-simple-file-backup-linux.html).
{:tip}

## Obtention d'aide en ligne

Les systèmes de portail {{site.data.keyword.backup_notm}} disposent d'une documentation complète et le support de l'application est accessible depuis le portail {{site.data.keyword.backup_notm}}. Cliquez sur le point interrogation blanc dans un cercle bleu situé dans l'angle supérieur droit pour obtenir de l'**aide**. Cliquez sur un article ou une rubrique dans la barre de navigation sur le côté gauche pour afficher davantage d'informations.
