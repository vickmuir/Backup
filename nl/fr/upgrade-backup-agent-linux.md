---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Mise à niveau de l'agent de logiciel de sauvegarde pour Linux
{: #UpgradeinLinux}

L'agent de sauvegarde le plus récent peut être téléchargé depuis la section des liens rapides du tableau de bord de votre portail {{site.data.keyword.backup_notm}}.
{:tip}

Suite au processus de mise à niveau, vérifier que vous pouvez mettre à niveau votre agent {{site.data.keyword.backup_notm}} sans perdre l'enregistrement

1. Connectez-vous à votre hôte au niveau racine.
2. Téléchargez la version la plus récente de l'agent.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. Extrayez le contenu du fichier téléchargé.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. Accédez au répertoire de l'installation récente.
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. Exécutez le script d'installation.
   ```
   ./install.sh
   ```
   {:pre}

6. Répondez aux invites en sélectionnant votre langue puis `N` pour ne pas enregistrer l'ordinateur en tant que nouvel hôte et `A` pour chiffrer les données en utilisant la méthode de chiffrement intégrée.

7. Si l'installation réussit, l'agent est enregistré dans `/opt/BUAgent/Install.log`.
