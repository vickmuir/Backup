---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Configuration de {{site.data.keyword.backup_notm}} sous Windows 2016
{: #InstallinWindows2016}

## Installation de l'agent de sauvegarde

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Cliquez deux fois sur le fichier téléchargé, puis cliquez sur **Exécuter** dans la boîte de dialogue qui s'affiche.
3. Sélectionnez la langue d'installation, puis cliquez sur **OK**.
4. Cliquez sur **Suivant** pour commencer.
5. Lisez les dispositions et sélectionnez **J'accepte les termes du contrat de licence**. Cliquez ensuite sur **Suivant**.
6. Sélectionnez **Standard** comme type d'installation. cliquez sur **Suivant**.
7. Sur l'écran Enregistrer l'agent auprès du portail, sélectionner **Ignorer l'enregistrement**. Cliquez sur **Suivant**.
8. Dans l'écran suivant, cliquez sur **Installer**.
9. Une fois l'installation achevée, cliquez sur **Terminer**.

## Installation de Central Control 8.30

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Cliquez deux fois sur le fichier téléchargé, puis cliquez sur **Exécuter** dans la boîte de dialogue qui s'affiche.
3. Suivez la procédure d'installation **standard**.
   1. Lorsque vous êtes invité à ajouter un raccourci sur le bureau, sélectionnez **Oui**. cliquez sur **Suivant**.
   2. Après avoir lu le contrat de licence du logiciel, sélectionnez **ACCEPTER**. cliquez sur **Suivant**.
   3. Conservez le dossier de destination, puis cliquez sur **Suivant**.
4. Lorsque l'installation est terminée, cochez **Lancer le logiciel CentralControl pour EVault**. Cliquez sur **Terminer**.


## Configuration de Central Control

Cette tâche est réalisée par le biais d'une série d'interactions alors que vous êtes connecté au serveur désigné pour le service {{site.data.keyword.backup_notm}}.

1. Contrôlez votre serveur à distance via RDP.
2. Démarrez Central Control.
3. Dans l'espace de travail, cliquez avec le bouton droit de la souris sur **My Agent** et sélectionnez l'option relative à la configuration d'agent.
4. Sur l'onglet Coffres, cliquez sur **Nouveau**. L'assistant de configuration de coffre s'affiche. cliquez sur **Suivant**.
5. Sélectionnez **Enregistrer en tant que nouvel ordinateur** et cliquez sur **Suivant**.
6. Entrez le nom du coffre dans la zone Nom de profil.

   Le nom du coffre peut être obtenu à partir du portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
   {:tip}
6. Entrez l'adresse réseau (adresse IP du coffre affecté) et cliquez sur **Ajouter**. Cliquez ensuite sur **Suivant**.
7. Entrez les nouvelles valeurs de port et cliquez sur **Ajouter**, puis sur **Suivant**.
8. Sur l'écran Paramètres de connexion, entrez le nombre de secondes et de minutes souhaité. Laissez cochée la case relative au chiffrement simultané pour les transmissions vers/depuis le coffre. cliquez sur **Suivant**.
9. Sur l'écran d'authentification, entrez vos données d'identification et cliquez sur **Suivant**.
10. La fenêtre Ordinateurs enregistrés indique le nom d'hôte de votre serveur. cliquez sur **Suivant**.
11.	Cliquez sur **Terminer** pour terminer la configuration.


## Création de schémas de conservation

1. Contrôlez votre serveur à distance via RDP.
2. Démarrez Central Control.
3. Dans l'espace de travail, cliquez avec le bouton droit de la souris sur **My Agent** et sélectionnez l'option relative à la configuration d'agent.
4. Cliquez sur l'onglet **Conservation**. L'assistant de conservation s'affiche. Cliquez sur **Suivant**.
5. Entrez le nom de la conservation. cliquez sur **Suivant**.<br/>

   L'entrée peut contenir un maximum de 32 caractères alphanumériques. Les espaces ne sont pas autorisés, à l'inverse des traits de soulignement (`_`) et des tirets (`-`).
   {:important}
6. Entrez le nombre de jours et de copies de conservation en ligne pour ce type de conservation. Cliquez ensuite sur **Suivant**.<br/>

   Le fait de définir conjointement un nombre de jours et de copies de conservation permet de garantir une durée minimale de conservation et un nombre minimal de sauvegardes conservées.
   {:tip}
7. Sélectionnez **Je ne souhaite pas créer des archives de copies de sauvegarde**. cliquez sur **Suivant**.
8. Cliquez sur **Terminer** pour achever la configuration du schéma de conservation.


## Configuration du travail de sauvegarde

1. Contrôlez votre serveur à distance via RDP.
2. Démarrez Central Control.
3. Dans l'espace de travail, cliquez avec le bouton droit de la souris sur **My Agent** et sélectionnez **Nouveau travail**.
4. Sur l'écran d'accueil, cliquez sur **Suivant**.
5. Sélectionnez le type de source de la sauvegarde.
6. Sélectionnez **Unicode** pour le codage. cliquez sur **Suivant**.
7. Sélectionnez la destination de ce travail. cliquez sur **Suivant**.
8. Entrez le nom et la description du travail.<br/>

   Le nom doit comporter entre 1 et 30 caractères. Il peut contenir des lettres, des chiffres, des traits de soulignement (`_`), des traits d'union (`-`) et des symboles du dollar (`$`).
   {:important}
9. Sélectionnez les sources de données. Cliquez sur **Ajouter**.
10. Spécifiez les options relatives à l'heure de la sauvegarde et du traitement. Cochez la case **Analyse de fichier rapide** et entrez les heures ou les minutes qui définissent votre fenêtre de sauvegarde. Cliquez ensuite sur **Suivant**.
11. Sélectionnez le type de chiffrement (la valeur par défaut est AES 256-bit) et entrez votre mot de passe de chiffrement. Cliquez sur **Suivant**.
12. Sélectionnez les options de consignation pour votre travail. Cochez la case **Créer un fichier journal** et sélectionnez **Purger automatiquement uniquement les fichiers journaux expirés**. Cliquez ensuite sur **Suivant**.
13. Sélectionnez **Quitter cet assistant**, puis cliquez sur **Terminer** pour terminer la configuration. Le nouveau travail s'affiche désormais sous My Agent.


## Exécution du travail de sauvegarde

1. Contrôlez votre serveur à distance via RDP.
2. Démarrez Central Control.
3. Dans l'espace de travail, cliquez avec le bouton droit de la souris sur **My Agent** et sélectionnez l'agent que vous venez de créer.
4. Sur l'écran d'accueil, cliquez sur **Suivant**.
5. Sélectionnez la destination de sauvegarde ou un autre emplacement pour alimenter le travail de sauvegarde. cliquez sur **Suivant**.<br/>
   Pour plus d'informations sur les coffres multiples, voir [Utilisation de coffres multiples](/docs/infrastructure/Backup?topic=Backup-multivault).
   {:tip}
6. Sélectionnez l'option d'analyse de fichier rapide pour que les fichiers qui n'ont pas été modifiés ne soient pas lus. cliquez sur **Suivant**.
7. Cliquez sur **Terminer** pour achever la configuration et lancer la sauvegarde. Une fenêtre d'informations de processus s'affiche ; elle contient l'état du travail de sauvegarde. Lorsque le travail de sauvegarde est terminé, cliquez sur **Fermer**.
