---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-29"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installation de vSphere Recovery Agent
{: #VRA}

vSphere Recovery Agent (VRA) est une application Windows qui permet de sauvegarder et restaurer des disques VMDK de jusqu'à 10 To. Vous pouvez installer vSphere Recovery Agent sur une machine physique ou virtuelle dotée d'un accès réseau local au vCenter que vous souhaitez protéger. Pour optimiser les performances, installez VRA sur une machine appartenant au même sous-réseau que vCenter. Pour répartir la charge de travail, un maximum de cinq VRA peuvent protéger les machines virtuelles qui sont attachées à un vCenter.

Dans une grappe étendue vSAN, chaque machine virtuelle possède un site préféré. Dans une situation idéale, une seule VRA locale est installée dans chaque site et sauvegarde les machines virtuelles préférées de ce site. Si une machine virtuelle est déplacée vers un site différent (en raison d'une maintenance ou d'une défaillance), la performance de la sauvegarde peut être dégradée mais elle reste acceptable.


## Commande du plug-in
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}} fournit vSphere Recovery Agent (VRA) gratuitement. Si vous bénéficiez actuellement d'un abonnement à {{site.data.keyword.backup_notm}}, vous pouvez télécharger le plug-in sur le portail {{site.data.keyword.backup_notm}}.

## Installation du plug-in
{: #installVRAPlugin}

Assurez-vous que la gestion de l'alimentation est désactivée sur le serveur sur lequel vous installez VRA.
{: important}

1. Téléchargez le kit d'installation à l'adresse `http://downloads.service.softlayer.com/evault/`. Ensuite, double-cliquez sur le kit d'installation.
2. Sur le message de confirmation, cliquez sur **YES**.
3. Sur la page d'accueil, cliquez sur **Next**.
4. Sur la page End User License Agreement, lisez le contrat de licence. Si vous acceptez les termes, cliquez sur **I accept the terms in the License Agreement**, puis cliquez sur **Next**.
5. Sur la page Destination Folder, effectuez l'une des actions suivantes.
   * Pour installer VRA dans l'emplacement par défaut, cliquez sur **Next**.
   * Pour installer VRA dans un autre emplacement, cliquez sur **Change**. Dans la boîte de dialogue Change destination folder, accédez au nouveau dossier d'installation ou tapez-le dans la zone Folder name. Cliquez sur **OK**. Sur la page Destination Folder, cliquez sur **Next**.
6. Sur la page Register Agent with Portal, spécifiez les informations suivantes.
   * Dans la zone **Network address**, entrez `ev-webcc01.service.softlayer.com`.
   * Dans la zone **Port**, entrez `8086`.
   * Dans la zone **Username**, tapez le nom d'utilisateur {{site.data.keyword.backup_notm}} responsable de gérer vSphere Recovery Agent.
   * Dans la zone **Password**, tapez le mot de passe de l'utilisateur {{site.data.keyword.backup_notm}} spécifié.
7.	Cliquez sur **Next**. Une fois l'installation achevée, cliquez sur **Finish**.

## Configuration de vSphere Recovery Agent
{: #configureVRA}

Une fois que vSphere Recovery Agent est installé, vous devez le configurer dans le portail {{site.data.keyword.backup_notm}}.

1. Connectez-vous au portail {{site.data.keyword.backup_notm}}. Pour en savoir plus sur l'accès au portail {{site.data.keyword.backup_notm}}, voir le [Tutoriel d'initiation](/docs/infrastructure/Backup?topic=Backup-gettingstarted#accessingWebCC).
2. Sur l'onglet Computers, sélectionnez le serveur pour lequel vous souhaitez effectuer une sauvegarde.
3. Configurez vos informations de coffre.

   Les informations de coffre peuvent être configurées de deux façons : **automatiquement** ou **manuellement**.<br/>Si vous configurez l'agent pour la première fois, vous pouvez utiliser l'option [Configuration automatique](#VRAautoconfig).<br/>Si l'ordinateur a été enregistré avec un coffre auparavant, la configuration automatique ne fonctionnera pas et le coffre devra être [configuré manuellement](#VRAmanualconfig).
   {: tip}

4. Configurez les [paramètres vCenter](#vCenterSettingsconfig)   

### Configuration automatique du coffre
{: #VRAautoconfig}

Pour configurer les paramètres du coffre de manière automatique, cliquez sur **Configure Automatically**. L'assistant de configuration s'exécute et configure les paramètres du coffre pour vous. Une fois l'opération terminée, cliquez sur **Go To Agent** pour vérifier les informations qui apparaissent dans l'onglet **Vault Settings**.
 

### Configuration manuelle du coffre
{: #VRAmanualconfig}

Pour configurer les paramètres du coffre manuellement, cliquez sur **Configure Manually**.   
1. Cliquez sur **Vault Settings**.
2. Cliquez sur **Add Vault**. La fenêtre Vault Settings s'affiche. Sous les options **Vault Profile**, sélectionnez le coffre approprié.
   Si l'ordinateur a été enregistré auparavant avec un coffre {{site.data.keyword.backup_notm}}, toutes les informations sont remplies automatiquement lorsque le coffre est sélectionné sous Vault Profile.
   {:note}

3. Vérifiez que toutes les informations de la page Vault settings sont correctes puis cliquez sur **Save**.
4. Lorsque vous sauvegardez les paramètres de coffre, les informations sur le coffre deviennent visibles dans l'onglet **Vault Settings**.


### Configuration des paramètres d'agent vCenter
{: #vCenterSettingsconfig}
Une fois l'enregistrement du coffre réussi, vous devez configurer les paramètres de vCenter avant de pouvoir créer et exécuter des travaux de sauvegarde.

1. Cliquez sur l'onglet **vCenter Settings**
2. Fournissez l'adresse IP, le nom de domaine et les données d'identification du vCenter que vous souhaitez protéger.
   L'utilisateur doit avoir un accès administrateur au vCenter pour pouvoir effectuer cette tâche.
   {:note}

3. Désactivez Change Block Tracking (CBT) en supprimant la coche. CBT est une fonctionnalité VMware qui détecte les secteurs de disque modifiés et améliore les performances des sauvegardes de machines virtuelles, qui est automatiquement activée par l'agent VSphere.
4. Cliquez sur **Test vCenter Connection**. Une nouvelle fenêtre affiche les résultats. Si les informations de connexion fournies sont correctes, le message suivant s'affiche : “The vCenter credentials have been validated successfully”.
5. Cliquez sur **Save** pour sauvegarder les paramètres. 

## Etapes suivantes
{: #VRAnextteps}
1. [Configurer, planifier et exécuter un travail de sauvegarde](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA#VConfigureVRA)
2. [Restaurer des données vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir accéder au guide d'utilisation et le télécharger depuis la documentation [{{site.data.keyword.backup_notm}} téléchargeable ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.
{:tip}
