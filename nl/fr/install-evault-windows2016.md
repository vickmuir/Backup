---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuration d'EVault sous Windows 2016

Actuellement, EVault WebCC n'est pas officiellement pris en charge sous Windows 2016. Les serveurs opérant sous Windows 2016 doivent utiliser le logiciel Windows Central Control.

## Installation de l'agent de sauvegarde EVault

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable :
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Double-cliquez sur le fichier téléchargé, puis cliquez sur **Exécuter** dans la boîte de dialogue en incrustation qui apparaît.
3. Sélectionnez la langue d'installation et cliquez sur **OK**.
4. Sélectionnez **Standard** pour le type d'installation. Cliquez sur **Suivant**.
5. Sur l'écran Enregistrer l'agent auprès du portail, sélectionner **Ignorer l'enregistrement**. 
6. Cliquez sur **Suivant**, puis sur **Terminer**.

## Installation du logiciel CentralControl pour EVault

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Double-cliquez sur le fichier téléchargé, puis cliquez sur **Exécuter** dans la boîte de dialogue en incrustation qui apparaît.
3. Suivez la procédure d'installation standard.

## Configuration de CentralControl

Cette tâche est réalisée par le biais d'une série d'interactions alors que vous êtes connecté au serveur désigné pour le service de sauvegarde EVault.

1. Contrôle à distance de votre serveur via RDP.
2. Lancement de CentralControl.
3. Dans l'espace de travail, cliquez avec le bouton droit sur **Agent** et sélectionnez **Configuration d'agent**.
4. Cliquez sur **Nouveau**.
5. Sélectionnez **Enregistrer en tant que nouvel ordinateur** et cliquez sur **Suivant**.
6. Entrez l'adresse réseau et cliquez sur **Ajouter**, puis sur **Suivant**.
7. Entrez les nouvelles valeurs de port et cliquez sur **Ajouter**, puis sur **Suivant**.
8. Sur l'écran Paramètres de connexion, entrez le nombre de secondes/minutes souhaité. 
9. Sur l'écran d'authentification, entrez vos données d'identification et cliquez sur **Suivant**.
10. La fenêtre Ordinateurs enregistrés indique le nom d'hôte de votre serveur. Cliquez sur **Suivant**.
11.	L'assistant Configuration du coffre a fini de collecter vos informations. Cliquez sur **Terminer** pour compléter l'enregistrement.


