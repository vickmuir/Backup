---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauration d'une image de volume système BMR
{: #restoreBMR}

Si vous avez besoin de restaurer une sauvegarde d'image bare metal depuis {{site.data.keyword.backup_full}}, vous pouvez le faire rapidement depuis le système BMR Rescue Kernel. BMR permet de restaurer le système sans qu'un système d'exploitation amorçable ne soit nécessaire. Cela est très utile si le système d'exploitation n'est plus utilisable ou que les unités du système ont été remplacées.

## Initialisation du système BMR Rescue Kernel

Vous pouvez accéder au système BMR Rescue Kernel via la console {{site.data.keyword.cloud_notm}}.
1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Cliquez sur la **flèche** en regard du coffre.
4. Cliquez sur **Lancer Bare Metal Restore**. Cette action déclenche une transaction dont l'exécution prend quelques minutes. Vous pouvez ensuite accéder au serveur en suivant la procédure décrite ici. Un message électronique vous est envoyé à l'issue du processus d'amorçage du système.


## Restauration depuis le noyau BMR Rescue Kernel

1. Une fois la transaction BMR Rescue Kernel chargée, vous pouvez y accéder de deux manières différentes.
  - Via un client VNC et l'adresse IP privée ou publique de votre serveur et le mot de passe répertorié dans la console {{site.data.keyword.cloud_notm}}.
  - Via la console KVM de votre carte IPMI.
  Les deux méthodes fonctionnent bien.
2. Lorsque vous vous connectez pour la première fois à BMR Rescue Kernel, vous êtes accueilli par un écran de sélection de langue. Sélectionnez celle de votre choix, puis cliquez sur **Suivant**.
<br/>![Figure 1 - Sélection de langue BMR](/images/bmr1.png)<br/> Le contrat de licence du logiciel s'affiche.
3. Si vous acceptez les dispositions, cochez la case et cliquez sur **Suivant** pour continuer. <br/> Le menu de restauration système principal d'{{site.data.keyword.backup_notm}} s'affiche.
4. Sélectionnez **Restaurer mon système**.
<br/>![Figure 2 - Menu BMR principal](/images/bmr2.png)
5. L'assistant de restauration système s'affiche. Sélectionnez **Suivant** pour continuer.
<br/>![Figure 3 - Assistant BMR](/images/bmr3.png)
6. Sélectionnez le type de sauvegarde depuis lequel effectuer la restauration. Sélectionnez **Logiciel EVault**, puis cliquez sur **Suivant** pour continuer.
7. Sur l'écran **Emplacement de la sauvegarde**, sélectionnez le coffre et entrez son adresse, le numéro de compte, ainsi que le nom d'utilisateur et le mot de passe. Cliquez ensuite sur **Suivant** pour continuer.
<br/>![Figure 4 - Sélection de l'emplacement de la sauvegarde](/images/bmr4.png)
8. Sur l'écran suivant, votre système est présent dans la liste. Vérifiez qu'il est mis en évidence et cliquez sur **Suivant**.
<br/>![Figure 5 - Sélection de votre système](/images/bmr5.png)
9. Sur l'écran **Sélection du travail de sauvegarde**, sélectionnez le travail à partir duquel effectuer la restauration et cliquez sur **Suivant**.
<br/>![Figure 6 - Sélection de votre point de restauration](/images/bmr6.png)
10. Dans le menu **Sélection du point de restauration**, effectuez une sélection et cliquez sur **Suivant**.
<br/>![Figure 8 - Sélection d'un point de restauration](/images/bmr8.png)
11. Sélectionnez les volumes source et de destination. Pour restaurer la source sur la destination,, faites glisser le volume source sur le volume de destination.
<br/>![Figure 9 - Sélection de volumes source et de destination](/images/bmr9.png)
12. Dans la fenêtre de confirmation du format ou de fusion des données, deux options sont présentées. Sélectionnez **Format** pour une restauration avec nettoyage, laquelle formate le disque. Si vous désirez fusionner les données sur le volume de destination, sélectionnez **Fusionner**.
<br/>![Figure 10 - Sélection d'une fusion](/images/bmr10.png)
13. Sur l'écran principal du volume source et de destination, cliquez sur **Suivant**.
14. Sur l'écran récapitulatif du plan de restauration, cochez la case pour accepter le plan et cliquez sur **Suivant**.
<br/>![Figure 11 - Lancement de la restauration](/images/bmr11.png)
15. L'écran de progression de la restauration s'affiche et indique la progression de l'opération.
<br/>![Figure 12 - Progression de la restauration](/images/bmr12.png)
16. A son terme, une fenêtre de notification vous avise que la restauration a abouti. Cliquez sur **OK**.
17. Sur l'écran de progression de la restauration, cliquez sur **Suivant**.
18. Sur l'écran final, cochez la case de redémarrage du système et sélectionnez **Terminer**. Le serveur charge votre image de volume restaurée.
  La restauration est à présent terminée. <br/>

  Lors du premier redémarrage du serveur, un message d'arrêt inattendu peut s'afficher. Cela est tout à fait normal avec ce type de sauvegarde ; ce message disparaît après le premier amorçage.
  {:tip}
