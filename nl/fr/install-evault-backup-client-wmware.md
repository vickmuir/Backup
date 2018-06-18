---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Installation du client de sauvegarde EVault pour VMware

L'installation du client de sauvegarde EVault sur un serveur VMware peut être réalisée via une série de commandes de shell ou de terminal depuis le serveur cible ESX. Cette procédure décrit les étapes requises pour l'installation du client de sauvegarde EVault sur votre serveur VMware :

Pour installer l'agent, téléchargez et copiez le package `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` sur le serveur ESX cible à l'aide de la commande suivante :

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**Remarque**: vous devez exécuter les étapes suivantes en local sur le serveur ESX cible.

1. Extrayez les fichiers du package. Pour ce faire, utilisez la commande suivante (où "PACKAGENAME" pourrait être “Agent-VMware-ESX-Server-6.71”) :
    `tar xvfz PACKAGENAME.tar.gz`
2. Accédez au répertoire où vous avez décompressé le package.
3. Exécutez le script d'installation :
    `# ./install.sh`

    **Remarque** :  le script d'installation vous réclame en mode interactif des informations de configuration telles que l'enregistrement Web (adresse, numéro de port et authentification) et le nom du fichier journal.
     
    - Entrez le nom d'utilisateur WebCC pour ce serveur.
    - Entrez le mot de passe WebCC pour ce serveur.
     
4. Entrez le **Nom d'utilisateur de la sauvegarde EVault** comme réponse à l'invite réclamant le nom d'utilisateur WebCC. 
5. Entrez le **Mot de passe de la sauvegarde EVault** comme réponse à l'invite réclamant le mot de passe WebCC.
6. Une fois l'installation terminée, un message de fin s'affiche, et le démon de l'agent sera en exécution.


### Autres remarques relatives à l'installation :
Si l'installation a abouti, un fichier Install.log sera présent sous le répertoire d'installation.
Par exemple : `/opt/BUAgent/Install.log`

Si l'installation échoue et est annulée, je journal d'installation figurera sous `<Installation Failure directory>`.
Si l'installation échoue sans être suivie de son annulation, le journal d'installation figurera sous `<Installation Kit directory>`.

Pour plus d'informations, téléchargez le manuel [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}. Prenez soin d'être connecté au {{site.data.keyword.BluVPN}} pour pouvoir voir ce lien.
