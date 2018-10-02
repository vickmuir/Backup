---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-10"

---
{:new_window: target="_blank"}


# Foire aux questions

## **Quel type d'applications peut être sauvegardé avec EVault ?**

EVault peut être utilisé pour sauvegarder diverses applications. Toutefois, {{site.data.keyword.BluSoftlayer_full}} propose des agents de logiciel pour certains des systèmes logiciels les plus courants qui sont sauvegardés, notamment :

- Bare Metal Restore
- Microsoft SQL
- Oracle

Les plug-in répertoriés ici ne sont compatibles qu'avec des serveurs Windows, à l'exception du plug-in Oracle. Chaque agent est disponible en tant que module complémentaire pour votre service de sauvegarde EVault. Pour ajouter un agent à votre service, contactez dès maintenant un membre de l'équipe commerciale.  

<hr>

## **A quelle fréquence les données peuvent-elles être sauvegardées à l'aide d'EVault ?**

Vous pouvez sauvegarder vos données aussi souvent que vous le souhaitez. Dans WebCC, les sauvegardes peuvent être effectuées manuellement ou planifiées en tant qu'instance unique à exécution récurrente. Les sauvegardes récurrentes peuvent être réalisées sur une base quotidienne, hebdomadaire, ou d'après un planning personnalisé, et peuvent être modifiées n'importe quand.

>**Remarque** : les sauvegardes très fréquentes s'exécutant plusieurs fois par jour ou par heure peuvent endommager les travaux de sauvegarde. Cela se produit car il se peut que le coffre ne parvienne pas à supprimer les anciens jeux sécurisés ou à effectuer d'autres tâches d'arrière-plan requises entre les exécutions.

<hr>

## **Comment les schémas de conservation fonctionnent-ils ?**

EVault permet une conservation des données en fonction de la durée à laquelle vous désirez pouvoir remonter. Le schéma de conservation **Quotidienne** conserve les données pendant 7 jours, tandis que les schémas **Hebdomadaire** les conservent pendant 1 mois et les schémas **Mensuelle** pendant 1 an. A la fin de chaque période, les données les plus anciennes sont expurgées et la première "sauvegarde delta" effectuée devient le point de restauration le plus éloigné disponible. 

<hr>

## **En quoi consiste la technologie Delta ?**

La toute première sauvegarde est une sauvegarde "de départ" (complète et intégrale), la suivante et les autres étant de type "delta" (à savoir, uniquement des modifications), mais qui sont équivalentes et considérées elles-aussi comme des "sauvegardes complètes". En d'autres termes, vous pouvez restaurer tous les fichiers, ou ceux de votre choix, depuis celle-ci. Cette technologie permet d'effectuer des "sauvegardes complètes" à chaque session, mais économise un espace considérable dans le coffre et réduit la durée d'exécution de chaque sauvegarde ultérieure.

<hr>

## **Les sauvegardes sont-elles sécurisées ?**

Par défaut, tous les chiffrements en ligne (OTW) utilisent un chiffrement AES 256 bits. Vous pouvez également choisir de stocker les données sous un format chiffré avec le protocole AES 256 bits. 

>**Remarque** : vous devez mémoriser votre mot de passe de chiffrement. Vos données ne peuvent pas être restaurées sans votre mot de passe. Si vous perdez votre mot de passe, vous ne pourrez pas récupérer vos données. 

Les ratios de compression admettent une compression allant de 0 % jusqu'à une compression maximale pouvant aller, selon le type de fichier, de 20 à 30 %.

<hr>

## **Quelles sont les informations stockées avec les sauvegardes de l'état du système ?**

Les sauvegardes de l'état du système incluent, sans s'y limiter, la base de données d'enregistrement de classe COM +, le registre, les fichiers d'amorçage, les fichiers système et le compteur de performance. Tout dépend de votre système. Les fichiers système varient selon le système d'exploitation et les service packs. On en compte généralement plusieurs milliers. MS Windows établit une liste dynamique de ces DLL lorsque vous les incluez dans la sauvegarde. Le fait d'inclure des fichiers système vous permet d'effectuer une reprise en cas de fichiers système endommagés ou si vous désinstallez par inadvertance des service packs, ou si vous désirez effectuer une restauration bare metal. Vous pouvez revenir à l'état de la sauvegarde sans avoir à réinstaller le système d'exploitation depuis le kit d'installation, puis d'installer chaque service pack séparément.

>**Remarque** : aucun fichier de données utilisateur n'est inclus dans une sauvegarde de l'état du système. Un travail de sauvegarde de l'état du système doit être configuré en tant que travail autonome. Aucune autre source de données ne doit être incluse dans le travail de sauvegarde de l'état du système.

<hr>

## **Que se passe-t-il pour les fichiers ouverts ?**

Par défaut, le client de base dispose d'une technologie de pointe lui permettant de traiter la plupart des fichiers ouverts qui s'exécutent sur le système d'exploitation.

<hr>

## **Où puis-je trouver des informations sur la tarification ?**

Pour plus d'informations, voir [Backup storage](https://www.ibm.com/cloud/backup-and-restore){:new_window} et [EVault on IBM Cloud: Pricing](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## **La capacité EVault peut-elle être augmentée/réduite sans compromettre les sauvegardes ?**

Vous pouvez augmenter ou réduire la taille de votre EVault via le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. La modification de la capacité EVault n'a aucun impact sur l'intégrité des données qui sont stockées dans le coffre. Pour plus d'informations, voir [Extension de la capacité EVault](expanding-evault-capacity.html).

<hr>

## **Que se passe-t-il lorsque la capacité EVault est dépassée ?**

Vous pouvez toujours enregistrer et récupérer vos sauvegardes même si vous avez atteint la limite de la capacité que vous avez achetée. Toutefois, vous devez vous attendre à des frais supplémentaires pour chaque Go additionnel utilisé au niveau de la facturation.

<hr>

## **Comment configurer des notifications dans WebCC pour savoir si des sauvegardes échouent ?**

Vous pouvez configurer des notifications dans l'onglet Avancé. Suivez les instructions qui figurent dans les **Liens rapides** de WebCC.
