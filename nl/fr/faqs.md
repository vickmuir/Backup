---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Foire aux questions

## Quel type d'applications peut être sauvegardé ?
{: faq}

{{site.data.keyword.backup_full}} peut être utilisé pour sauvegarder diverses applications. Toutefois, {{site.data.keyword.BluSoftlayer_full}} propose des agents de logiciel pour certains des systèmes logiciels les plus courants qui sont sauvegardés, notamment :

- Bare Metal Restore
- Microsoft Exchange
- Microsoft SQL
- Oracle

Les plug-in répertoriés ici ne sont compatibles qu'avec des serveurs Windows, à l'exception du plug-in Oracle. Chaque agent est disponible en tant que module complémentaire pour votre service de sauvegarde. Pour ajouter un agent à votre service, contactez dès maintenant un membre de l'équipe commerciale.

<hr>

## A quelle fréquence les données peuvent-elles être sauvegardées ?
{: faq}

Dans WebCC, les sauvegardes peuvent être effectuées manuellement ou planifiées en tant qu'instance unique ou à exécution récurrente. Les sauvegardes récurrentes peuvent être réalisées sur une base quotidienne, hebdomadaire, ou d'après un planning personnalisé, et peuvent être modifiées n'importe quand.

Les sauvegardes très fréquentes s'exécutant plusieurs fois par jour ou par heure peuvent endommager les travaux de sauvegarde. Cela se produit car le coffre de sauvegarde n'a pas suffisamment de temps pour exécuter les tâches de maintenance en arrière-plan qui sont requises. Les travaux de sauvegarde sont prioritaires sur les taches de maintenance. Par conséquent, en cas de sauvegardes extrêmement fréquentes, le coffre continue à exécuter les travaux de sauvegarde, ce qui provoque l'augmentation du nombre de jeux sécurisés.
{:note}

<hr>

## Comment les schémas de conservation fonctionnent-ils ?
{: faq}

{{site.data.keyword.backup_notm}} permet une conservation des données en fonction de la durée à laquelle vous désirez pouvoir remonter. Le schéma de conservation **Quotidienne** conserve les données pendant 7 jours, tandis que les schémas **Hebdomadaire** les conservent pendant 1 mois et les schémas **Mensuelle** pendant 1 an. A la fin de chaque période, les données les plus anciennes sont expurgées et la première "sauvegarde delta" effectuée devient le point de restauration le plus éloigné disponible.

Vous pouvez modifier les schémas de conservation par défaut et créer des schémas de conservation personnalisés. Toutefois, il est fortement recommandé d'utiliser les conservations par défaut pour commencer. Lorsque vous créez un nouveau schéma de conservation ou que vous modifiez un schéma de conservation existant, assurez-vous que l'option Archivage n'est pas cochée. L'archivage n'est pas pris en charge.
{:tip}

<hr>

## En quoi consiste la technologie Delta ?
{: faq}

La toute première sauvegarde est une sauvegarde "de départ" (complète et intégrale), la suivante et les autres étant de type "delta" (à savoir, uniquement des modifications), mais qui sont équivalentes et considérées elles-aussi comme des "sauvegardes complètes". En d'autres termes, vous pouvez restaurer tous les fichiers, ou ceux de votre choix, depuis celle-ci. Cette technologie permet d'effectuer des "sauvegardes complètes" à chaque session, mais économise un espace considérable dans le coffre et réduit la durée d'exécution de chaque sauvegarde ultérieure.

<hr>

## Les sauvegardes sont-elles sécurisées ?
{: faq}

Par défaut, tous les chiffrements en ligne (OTW) utilisent un chiffrement AES 256 bits. Vous pouvez également choisir de stocker les données sous un format chiffré avec le protocole AES 256 bits.

Vous devez mémoriser votre mot de passe de chiffrement. Vos données ne peuvent pas être restaurées sans votre mot de passe. Si vous perdez votre mot de passe, vous ne pourrez pas récupérer vos données.
{:important}

Les ratios de compression admettent une compression allant de 0 % jusqu'à une compression maximale pouvant aller, selon le type de fichier, de 20 à 30 %.

<hr>

## Quelles sont les informations stockées avec les sauvegardes de l'état du système ?
{: faq}

Les sauvegardes de l'état du système incluent, sans s'y limiter, la base de données d'enregistrement de classe COM +, le registre, les fichiers d'amorçage, les fichiers système et le compteur de performance. Tout dépend de votre système. Les fichiers système varient selon le système d'exploitation et les service packs. On en compte généralement plusieurs milliers. MS Windows établit une liste dynamique de ces DLL lorsque vous les incluez dans la sauvegarde. Le fait d'inclure des fichiers système vous permet d'effectuer une reprise en cas de fichiers système endommagés ou si vous désinstallez par inadvertance des service packs, ou si vous désirez effectuer une restauration bare metal. Vous pouvez revenir à l'état de la sauvegarde sans avoir à réinstaller le système d'exploitation depuis le kit d'installation, puis d'installer chaque service pack séparément.

Aucun fichier de données utilisateur n'est inclus dans une sauvegarde de l'état du système. Un travail de sauvegarde de l'état du système doit être configuré en tant que travail autonome. Aucune autre source de données ne doit être incluse dans le travail de sauvegarde de l'état du système.{:important}

<hr>

## Que se passe-t-il pour les fichiers ouverts ?
{: faq}

Par défaut, le client de base dispose d'une technologie de pointe lui permettant de traiter la plupart des fichiers ouverts qui s'exécutent sur le système d'exploitation.

<hr>

## Où puis-je trouver des informations sur la tarification ?
{: faq}

Pour plus d'informations, voir [Backup storage](https://www.ibm.com/cloud/backup-and-restore){:new_window} et [{{site.data.keyword.backup_notm}} on IBM Cloud: Pricing](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## La capacité  {{site.data.keyword.backup_notm}} peut-elle être augmentée/réduite sans compromettre les sauvegardes ?
{: faq}

Vous pouvez augmenter ou réduire la taille de votre coffre via le portail [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}. La modification de la capacité n'a aucun impact sur l'intégrité des données qui sont stockées dans le coffre. Pour plus d'informations, voir [Extension de la capacité](expanding-capacity.html).

<hr>

## Que se passe-t-il lorsque la capacité {{site.data.keyword.backup_notm}} est dépassée ?
{: faq}

Vous pouvez toujours enregistrer et récupérer vos sauvegardes même si vous avez atteint la limite de la capacité que vous avez achetée. Toutefois, vous devez vous attendre à des frais supplémentaires pour chaque Go additionnel utilisé au niveau de la facturation.

<hr>

## Comment configurer des notifications dans WebCC pour savoir si des sauvegardes échouent ?
{: faq}

Vous pouvez configurer des notifications dans l'onglet Avancé. Suivez les instructions qui figurent dans les **Liens rapides** de WebCC.
