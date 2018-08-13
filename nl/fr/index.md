---

copyright:
  years: 2014, 2018
lastupdated: "2018-07-10"

---
{:new_window: target="_blank"}

# Initiation aux services de sauvegarde EVault

Les sauvegardes permettent de stocker en toute sécurité vos données hors de votre appareil et de les protéger si celui-ci venait à être perdu. EVault est un système de sauvegarde basé sur un agent et automatisé qui est géré via l'utilitaire de gestion EVault WebCC reposant sur un navigateur. EVault fournit aux utilisateurs une méthode de sauvegarde des données entre les serveurs d'un ou de plusieurs centres de données sur le réseau {{site.data.keyword.BluSoftlayer_full}}. Les administrateurs peuvent faire en sorte que des sauvegardes soient effectuées toutes les heures, tous les jours, toutes les semaines ou définir des sauvegardes personnalisées qui ciblent des systèmes complets, des répertoires spécifiques ou même des fichiers individuels. Des plug-ins supplémentaires permettent la compatibilité avec des logiciels tels que Microsoft Exchange et Microsoft SQL, ainsi qu'avec d'autres types de logiciels tiers. Ils permettent également aux utilisateurs d'effectuer une restauration physique, en cas de besoin.

## Commande d'EVault 

Vous pouvez acquérir le service de sauvegarde EVault de deux manières.

- Acquisition d'EVault lors de la commande d'un serveur
- Acquisition d'EVault sous forme de mise à niveau

Pour plus d'informations sur la tarification, voir [Backup storage](https://www.ibm.com/cloud/backup-and-restore){:new_window} et [EVault on IBM Cloud](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Acquisition d'EVault lors de la commande d'un serveur

1. Connectez-vous au [catalogue IBM Cloud ](https://console.bluemix.net/catalog/){:new_window} ou au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Commandez un serveur "bare metal" facturé au mois. Cliquez [ici](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window} pour plus d'informations sur la commande de serveurs bare metal.
3. Vous êtes redirigé vers le portail de gestion pour passer votre commande. <br/>
   >**Remarque** : le service de sauvegarde EVault n'est pas disponible si vous commandez un serveur facturé sur une base horaire. Toutefois, vous pouvez ajouter ultérieurement le service sous forme de mise à niveau. 
4. Sous la section **Modules complémentaires**, sélectionnez l'une des options EVault (autre que "Aucune").
6. Faites défilez la page, puis cliquez sur **Ajouter à la commande**.
7. Accédez à la section des noms d'hôte et de domaine et entrez les noms d'hôte et de domaine. Vous pouvez choisir n'importe quel nom d'hôte et de domaine.
8. Sur la droite, cochez les cases **Conditions des services Cloud** et **Contrat de service tiers**.
9. Confirmez ou entrez vos informations de paiement et cliquez sur **Soumettre la commande**. Un écran incluant votre numéro de commande de mise à disposition s'affiche. Vous pouvez imprimer cette page car il s'agit de votre reçu de commande de mise à disposition. <br/>**Remarque **: vous pouvez également enregistrer cette commande sans acquérir le produit en cliquant sur **Enregistrer sous devis**.

Plusieurs messages électroniques sont envoyés à votre administrateur (accusé de réception de la commande de mise à disposition, approbation et traitement de la commande de mise à disposition et mise à disposition terminée). Le message électronique de mise à disposition de votre commande inclut un lien vers votre page *Détails de l'unité* une fois que vous vous connectez à {{site.data.keyword.cloud_notm}}. Vous pouvez également vous connecter directement au portail {{site.data.keyword.slportal}}.

**Confirmation de l'acquisition du service EVault**
1. Dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, sélectionnez **Unités** > **Liste des unités** dans le menu principal. 
2. Localisez le nouveau serveur vous avez commandé.
  - Si une icône en forme d'horloge figure en regard de l'URL, vous devez patienter avant de confirmer votre acquisition d'EVault. Vous pouvez actualiser la page pour voir un statut mis à jour sur votre nouveau serveur. Lorsque l'icône en forme d'horloge disparaît, vous pouvez passer aux étapes suivantes pour confirmer votre acquisition du service EVault.
  - Lorsque l'icône en forme d'horloge n'apparaît plus pour votre serveur, cliquez sur le lien (l'URL du serveur) afin d'accéder à la page **Détails de l'unité**. 
3. Cliquez sur l'onglet **Stockage** pour afficher les informations d'EVault.
4. Examinez la section EVault et vérifiez que la taille sélectionnée lors de la procédure d'acquisition d'EVault est affichée en regard du lien EVault.

### Acquisition d'EVault sous forme de mise à niveau

**Sélectionnez un serveur sur lequel installer EVault**
1. Connectez-vous au [catalogue IBM Cloud ](https://console.bluemix.net/catalog/){:new_window} ou au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Sélectionnez **Unités** > **Liste des unités** dans le menu principal. Recherchez le périphérique pour lequel vous désirez ajouter le service EVault.
3. Cliquez sur le nom de l'unité pour accéder à la page Détails de l'unité.

**Ajout (acquisition) du service EVault**
1. Cliquez sur l'onglet **Stockage** et faites défiler l'écran jusqu'à la section EVault. 
2. Cliquez sur le lien **Ajouter**.
3. Dans la fenêtre, sélectionnez un emplacement et choisissez une taille.
4. Sélectionnez Type de paiement et cliquez sur **Continuer**
5. Entrez un **code promo** si vous en avez un, puis cliquez sur **Recalculer**.
6. Vérifiez votre commande, puis cliquez sur le lien pour lire les dispositions. 
7. Cochez la case si vous acceptez les dispositions.
7. Cliquez sur **Valider la commande**.

**Confirmation de l'acquisition d'EVault par mise à niveau**
1. Actualisez la page **Détails de l'unité** et vérifiez que l'onglet **Stockage** est sélectionné.
2. Examinez la section EVault et vérifiez que la taille sélectionnée lors de la procédure d'acquisition d'EVault est affichée en regard du lien EVault.<br /> **Remarque** : si la taille du stockage EVault continue à afficher une capacité égale à zéro, actualisez à nouveau la page. 

## Accès et examen des détails du stockage du service de sauvegarde EVault dans le portail {{site.data.keyword.slportal}}

Vous pouvez examiner à tout moment les détails du stockage de votre service de sauvegarde EVault depuis le portail {{site.data.keyword.slportal}}. Les détails que vous pouvez consulter comprennent le mot de passe, l'adresse mémoire et l'utilisation qui sont associés au service de sauvegarde EVault sélectionné. 

1. Pour accéder à l'écran **Stockage de sauvegarde EVault**, connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} à l'aide de vos données d'identification uniques. 
2. Cliquez sur **Stockage** et sélectionnez **Sauvegarde** dans la liste. 
2. Cliquez n'importe où sur la ligne du coffre de sauvegarde EVault dont vous souhaitez examiner les informations de stockage. Dans cette vue, le mot de passe n'est pas visible. Passez à l'étape suivante pour examiner le mot de passe associé à votre service de sauvegarde EVault. 
3. Cochez la case **Afficher** en regard de la zone **Mot de passe** pour examiner le mot de passe du service de sauvegarde EVault sélectionné.

Dans de nombreux produits et services {{site.data.keyword.BluSoftlayer_full}}, la fonction de stockage du mot de passe dans le portail {{site.data.keyword.slportal}} est utilisée uniquement à des fins de stockage ou de suivi du mot de passe. Pour ces offres, les modifications qui sont apportées au mot de passe dans le portail {{site.data.keyword.slportal}} ne sont pas appliquées au produit ou au service.  

Ce n'est _pas_ le cas pour le service de sauvegarde EVault. Les modifications apportées au mot de passe de sauvegarde EVault dans le portail {{site.data.keyword.slportal}} sont appliquées au service proprement dit. Lorsque vous modifiez votre mot de passe, n'oubliez pas que cela impacte directement votre service. Pour réinitialiser votre mot de passe, suivez la procédure décrite dans [Modification d'un mot de passe EVault Backup dans le portail {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Installation de l'agent EVault

L'agent EVault est pris en charge sur les systèmes d'exploitation suivants :

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
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Suivez les instructions correspondant à votre système d'exploitation. 
- [Installation du client de sauvegarde EVault sous Linux](install-evault-backup-client-linux.html)
- [Installation du client de sauvegarde EVault sous Windows](install-evault-backup-client-windows.html)
- [Installation du client de sauvegarde EVault pour Windows 2016](install-evault-windows2016.html)

## Accès à WebCC (WebCentralControl) pour le service de sauvegarde EVault

WebCC (WebCentralControl) est le client qui est utilisé pour interagir avec un service de sauvegarde EVault offert par {{site.data.keyword.BluSoftlayer_full}}. WebCC est un client reposant sur un navigateur qui s'exécute sur le réseau privé {{site.data.keyword.BluSoftlayer_full}} et permet un contrôle complet d'un service de sauvegarde EVault, notamment pour la configuration et les restaurations. Procédez comme suit pour accéder à WebCC pour un service de sauvegarde EVault :

1. Accédez au réseau privé via VPN.<br/>**Remarque **: WebCC n'est pas accessible à travers le réseau public. Une connexion VPN doit d'abord être établie. 
2. Accédez à l'écran de stockage de sauvegarde EVault sur le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Cliquez n'importe où sur la ligne de la sauvegarde EVault concernée pour développer la vue.
4. Cliquez sur **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.

## Configuration de l'agent EVault dans WebCC

Une fois que vous avez commandé votre service EVault et que l'agent a été installé sur le serveur, vous pouvez commencer à créer des sauvegardes de vos données. Procédez comme suit pour configurer votre agent, le planning de conservation des données et entamer votre premier travail de sauvegarde.

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
   **Remarque ** - cliquez [ici](evault-backup-faq.html) pour plus d'informations sur les schémas de conservation des données.
5. Lancez l'agent et déclenchez une sauvegarde.
   1. Cliquez sur **Tous les agents**, puis sélectionnez celui que vous avez configuré. 
   2. Cliquez sur **Exécuter une sauvegarde**.
   3. Confirmez la destination de sauvegarde et sélectionnez un schéma de conservation des données.
   4. Cliquez sur **Lancer la sauvegarde**. Vous pouvez afficher les détails de la sauvegarde pendant l'exécution du processus.
   5. Une fois la sauvegarde terminée, cliquez sur **Fermer**.
   
>**Remarque** : cliquez [ici](configure-simple-file-backup-linux.html) pour obtenir davantage d'informations sur la configuration de sauvegardes simples au niveau fichier sur Linux.

## Obtention d'aide en ligne 

Les systèmes WebCC disposent d'une documentation complète et le support de l'application est accessible depuis WebCC. Cliquez sur le point interrogation blanc dans un cercle bleu situé dans l'angle supérieur droit pour obtenir de l'**aide**. Cliquez sur un article ou une rubrique dans la barre de navigation sur le côté gauche pour afficher davantage d'informations.


