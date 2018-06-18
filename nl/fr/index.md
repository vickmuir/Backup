---

copyright:
  years: 2014, 2018
lastupdated: "2018-06-05"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Initiation aux services de sauvegarde EVault

Les sauvegardes permettent un stockage sécurisé de vos données hors de votre appareil et de les protéger s'il venait à être perdu. EVault Backup est un système de sauvegarde basé agent et automatisé qui est géré via l'utilitaire EVault WebCC basé navigateur et qui fournit aux utilisateurs une méthode de sauvegarde des données entre les serveurs d'un ou de plusieurs centres de données sur le réseau {{site.data.keyword.BluSoftlayer_full}}. Les administrateurs peuvent faire en sorte que des sauvegardes soient effectuées toutes les heures, tous les jours, toutes les semaines ou définir des sauvegardes personnalisées qui ciblent des systèmes complets, des répertoires spécifiques ou même des fichiers individuels. Des plug-ins supplémentaires permettent la compatibilité avec des logiciels tels Microsoft Exchange et Microsoft SQL, ainsi qu'avec d'autres types de logiciels tiers. Ils permettent également aux utilisateurs d'effectuer une restauration physique sur un ordinateur nu ("Bare Metal Restore"), en cas de besoin.

## Commande d'EVault 

Vous pouvez faire l'acquisition du service de sauvegarde EVault de deux façons :

- En acquérant EVault lorsque vous commandez un serveur
- En acquérant EVault sous forme de mise à niveau

### Acquisition d'EVault lors de la commande d'un serveur

1. Connectez-vous au [catalogue IBM Cloud ](https://console.bluemix.net/catalog/){:new_window} ou au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Commandez un serveur "bare metal" facturé au mois. Cliquez [ici](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window} pour plus d'informations sur la commande de serveurs bare metal.
3. Vous êtes redirigé vers le portail de gestion pour passer votre commande. <br/>
  **Remarque **: le service de sauvegarde EVault n'est pas disponible si vous commandez un serveur facturé sur une base horaire. Toutefois, vous pouvez ajouter ultérieurement le service sous forme de mise à niveau. 
4. Sous la section **Modules complémentaires**, sélectionnez l'une des options EVault (autre que "Aucune").
6. Cliquez au-bas de la page sur **Ajouter à la commande**. La page Paiement s'affiche.
7. Sur la page **Paiement**, accédez à la section Hôte et nom de domaine et entrez les noms d'hôte et de domaine. Vous pouvez choisir n'importe quel nom d'hôte et de domaine.
8. Sur le côté droit de la page **Paiement**, cochez les cases **Conditions des services Cloud** et **Contrat de service tiers**.
9. Confirmez ou entrez vos informations de paiement et cliquez sur **Soumettre la commande**. Un écran incluant votre numéro de commande de mise à disposition s'affiche. Vous pouvez imprimer cette page car il s'agit de votre reçu de commande de mise à disposition. <br/>**Remarque **: vous pouvez également enregistrer cette commande sans acquérir le produit en cliquant sur **Enregistrer sous devis**.

Plusieurs messages électroniques sont envoyés à votre administrateur (accusé de réception de la commande de mise à disposition, approbation et traitement de la commande de mise à disposition et mise à disposition terminée). L'e-mail de mise à disposition de votre commande inclut un lien vers votre page *Détails de l'unité* une fois que vous vous connectez à {{site.data.keyword.cloud_notm}}. Vous pouvez également vous connecter directement au portail {{site.data.keyword.slportal}}.

**Confirmez l'acquisition du service EVault**
1. Dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, sélectionnez **Unités** > **Liste des unités** dans le menu principal. 
2. Localisez le nouveau serveur vous avez commandé.
  - Si une icône en forme d'horloge figure en regard de l'URL, vous devrez patienter avant de confirmer votre acquisition d'EVault. Vous pouvez actualiser la page pour voir un statut mis à jour sur votre nouveau serveur. Lorsque l'icône en forme d'horloge disparaît, vous pouvez passer aux étapes suivantes pour confirmer votre acquisition du service EVault.
  - Lorsque l'icône en forme d'horloge n'apparaît plus pour votre serveur, cliquez sur le lien (l'URL du serveur) afin d'accéder à la page **Détails de l'unité**. 
3. Cliquez sur l'onglet **Stockage** pour afficher les informations d'EVault.
4. Inspectez la section EVault et vérifiez que la taille sélectionnée lors de la procédure d'acquisition d'EVault est affichée en regard du lien EVault.

### Acquisition d'EVault sous forme de mise à niveau

**Sélectionnez un serveur sur lequel installer EVault**
1. Connectez-vous au [catalogue IBM Cloud ](https://console.bluemix.net/catalog/){:new_window} ou au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Sélectionnez **Unités** > **Liste des unités** dans le menu principal. Recherchez le périphérique pour lequel vous désirez ajouter le service EVault.
3. Cliquez sur le nom de l'unité pour accéder à la page Détails de l'unité.

**Ajoutez (acquérez) le service EVault**
1. Cliquez sur l'onglet **Stockage** et localisez la section EVault vers le bas de la page.
2. Cliquez sur le lien **Ajouter**.
3. Dans le menu contextuel, sélectionnez un emplacement ou acceptez la valeur par défaut et sélectionnez une taille.
4. Cliquez sur **Continuer**
5. Cochez la case si vous acceptez les dispositions.
6. Cliquez sur **Valider la commande**.

**Confirmez l'acquisition du service EVault**
1. Actualisez la page **Détails de l'unité** et vérifiez que l'onglet **Stockage** est sélectionné.
2. Inspectez la section EVault et vérifiez que la taille sélectionnée lors de la procédure d'acquisition d'EVault est affichée en regard du lien EVault.<br /> **Remarque **: si la taille du stockage EVault continue à afficher une capacité de zéro, actualisez à nouveau la page. 

## Accès et examen des détails du stockage de la sauvegarde EVault dans le portail {{site.data.keyword.slportal}}

Vous pouvez examiner à tout moment les détails du stockage de votre service de sauvegarde EVault depuis le portail {{site.data.keyword.slportal}}. Les détails que vous pouvez consulter comprennent le mot de passe, l'adresse mémoire et l'utilisation associés au service de sauvegarde EVault sélectionné. 

1. Pour accéder à l'écran **Stockage de sauvegarde EVault** dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, connectez-vous à l'aide de vos données d'identification uniques.
2. Cliquez sur **Stockage** et sélectionnez **Sauvegarde** dans la liste déroulante.
2. Cliquez n'importe où sur la ligne de la sauvegarde EVault désirée pour examiner ses informations de stockage. Dans cette vue, le mot de passe n'est pas visible. Passez à l'étape suivante pour examiner le mot de passe associé à votre service EVault Backup.
3. Cochez la case **Afficher** en regard de la zone **Mot de passe** pour examiner le mot de passe du service EVault Backup sélectionné.

Dans de nombreux produits et services {{site.data.keyword.BluSoftlayer_full}}, la fonction de stockage du mot de passe dans le portail {{site.data.keyword.slportal}} est utilisée uniquement à des fins de stockage ou de suivi du mot de passe et les modifications qui lui sont apportées dans le portail {{site.data.keyword.slportal}} ne sont pas appliquées au produit ou au service. Ceci n'est _pas_ le cas pour EVault Backup. Les modifications apportées au mot de passe EVault Backup dans le portail {{site.data.keyword.slportal}} sont appliquées au service lui-même. Si vous le modifiez, rappelez-vous que votre service sera directement impacté. Pour réinitialiser votre mot de passe, suivez la procédure décrite dans [Modification d'un mot de passe EVault Backup dans le portail {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Installation de l'agent EVault

L'agent EVault est pris en charge sur les systèmes d'exploitation suivants :

### Windows
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

### Linux
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Suivez les instructions correspondant à votre système d'exploitation :
- [Installation du client de sauvegarde EVault sous Linux](install-evault-backup-client-linux.html)
- [Installation du client de sauvegarde EVault sous Windows](install-evault-backup-client-windows.html)
- [Installation du client de sauvegarde EVault pour Windows 2016](install-evault-windows2016.html)

## Accès à WebCC (WebCentralControl) pour sauvegarde EVault

WebCC (WebCentralControl) est le client utilisé pour interaction avec un service EVault Backup offert par {{site.data.keyword.BluSoftlayer_full}}. WebCC est un client basé navigateur qui s'exécute sur notre réseau privé en permettant un contrôle complet d'un service EVault Backup, notamment pour la configuration et les restaurations. Procédez comme suit pour accéder à WebCC pour EVault Backup.

1. Accédez au réseau privé via VPN. <br/>
    **Remarque **: WebCC n'est pas accessible à travers le réseau public. Une connexion de réseau privé virtuel (VPN) doit être établie pour accéder à WebCC.
2. Accédez à l'écran Stockage de sauvegarde EVault sur le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Cliquez n'importe où sur la ligne de la sauvegarde EVault désirée pour développer la vue. 
3. Cliquez sur **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.

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
4. Créez un planning de conservation des données :
   1. Sélectionnez **Editer** > **Paramètres de l'agent**.
   2. Cliquez sur **Ajouter**.
   3. Renseignez les informations de conservation de vos données.
   4. Cliquez sur **OK**.
   5. Cliquez sur **Enregistrer**.
   **Remarque ** - cliquez [ici](evault-backup-faq.html#how-do-the-retention-schemes-work-) pour plus d'informations sur les schémas de conservation des données. 
5. Lancez l'agent et déclenchez une sauvegarde.
   1. Cliquez sur **Tous les agents**, puis sélectionnez celui que vous venez de configurer.
   2. Cliquez sur **Exécuter une sauvegarde**.
   3. Confirmez la destination de sauvegarde et sélectionnez un schéma de conservation des données.
   4. Cliquez sur **Lancer la sauvegarde**. Vous pouvez afficher les détails de la sauvegarde pendant l'exécution du processus.
   5. Une fois la sauvegarde terminée, cliquez sur **Fermer**.
   
**Remarque **: cliquez [ici](configure-simple-file-backup-linux.html) pour plus d'informations sur la configuration de sauvegardes simples au niveau fichier sur Linux.

## Que se passe-t-il ensuite ?

Les systèmes WebCC disposent d'une documentation complète et le support de l'application est accessible depuis WebCC. Cliquez sur l'icône **Aide** à l'angle supérieur droit, indiquée par un point d'interrogation blanc dans un cercle bleu. Cliquez sur un article ou une rubrique dans la barre de navigation à gauche de la boîte de dialogue en incrustation pour afficher plus d'informations.


