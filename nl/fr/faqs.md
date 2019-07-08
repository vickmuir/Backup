---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, backup frequency, backup types, backup retention scheme, plugins, delta technology, open files, pricing

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Foire aux questions
{: #faqs}

## Quel type d'applications peut être sauvegardé ?
{: faq}

{{site.data.keyword.backup_full}} peut être utilisé pour sauvegarder diverses applications. {{site.data.keyword.cloud}} propose également des agents de logiciel pour certains des systèmes logiciels les plus courants qui sont sauvegardés, notamment :

- [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

Les plug-in répertoriés ici ne sont compatibles qu'avec des serveurs Windows, à l'exception des plug-in Oracle et VMware. Chaque agent est disponible gratuitement en tant que module complémentaire de votre service de sauvegarde.

<hr>

## A quelle fréquence les données peuvent-elles être sauvegardées ?
{: faq}

Dans le portail {{site.data.keyword.backup_notm}}, les sauvegardes peuvent être effectuées manuellement ou planifiées en tant qu'instance unique ou à exécution récurrente. Les sauvegardes récurrentes peuvent être réalisées sur une base quotidienne, hebdomadaire, ou d'après un planning personnalisé, et peuvent être modifiées n'importe quand.

Les sauvegardes très fréquentes s'exécutant plusieurs fois par jour ou par heure peuvent endommager les travaux de sauvegarde. Cela se produit car le coffre de sauvegarde n'a pas suffisamment de temps pour exécuter les tâches de maintenance en arrière-plan qui sont requises. Les travaux de sauvegarde sont prioritaires sur les taches de maintenance. Par conséquent, en cas de sauvegardes extrêmement fréquentes, le coffre continue à exécuter les travaux de sauvegarde, ce qui provoque l'augmentation du nombre de jeux sécurisés.
{:note}

<hr>

## Comment les schémas de conservation fonctionnent-ils ?
{: faq}

{{site.data.keyword.backup_notm}} permet une conservation des données dépendant de la durée que vous choisissez. Le schéma de conservation **Quotidienne** conserve les données pendant 7 jours, tandis que les schémas **Hebdomadaire** les conservent pendant 1 mois et les schémas **Mensuelle** pendant 1 an. A la fin de chaque période, les données les plus anciennes sont expurgées et la première "sauvegarde delta" effectuée devient le point de restauration le plus éloigné disponible.

Vous pouvez modifier les schémas de conservation par défaut et créer des schémas de conservation personnalisés. IBM recommande toutefois d'utiliser les conservations par défaut pour commencer. Quand vous créez un nouveau schéma de conservation ou que vous modifiez un schéma de conservation existant, assurez-vous que l'option d'archivage n'est pas cochée. L'archivage n'est pas pris en charge.
{:tip}

<hr>

## En quoi consiste la technologie Delta ?
{: faq}

La toute première sauvegarde est une sauvegarde "de départ" (complète et intégrale), la suivante et les autres étant de type "delta" (à savoir, uniquement des modifications), mais qui sont équivalentes et considérées elles-aussi comme des "sauvegardes complètes". En d'autres termes, vous pouvez restaurer tous les fichiers, ou ceux de votre choix, depuis celle-ci. Avec cette technologie, des "sauvegardes complètes" sont créées à chaque session mais un espace considérable est économisé dans le coffre et la durée d'exécution de chaque sauvegarde suivante est réduite d'autant.

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

Les sauvegardes de l'état du système incluent, sans s'y limiter, la base de données d'enregistrement de classe COM +, le registre, les fichiers d'amorçage, les fichiers système et le compteur de performance. Tout dépend de votre système. Les fichiers système varient selon le système d'exploitation et les service packs. On en compte généralement plusieurs milliers. MS Windows établit une liste dynamique de ces DLL lorsque vous les incluez dans la sauvegarde. Le fait d'inclure des fichiers système vous permet d'effectuer une reprise en cas de fichiers système endommagés ou si vous retirez par inadvertance des service packs ou voulez effectuer une restauration bare metal. Vous pouvez revenir à l'état de la sauvegarde sans avoir à réinstaller le système d'exploitation depuis le kit d'installation, puis d'installer chaque service pack séparément.

Aucun fichier de données utilisateur n'est inclus dans une sauvegarde de l'état du système. Un travail de sauvegarde de l'état du système doit être configuré en tant que travail autonome. Aucune autre source de données ne doit être incluse dans le travail de sauvegarde de l'état du système.
{:important}

<hr>

## Que se passe-t-il pour les fichiers ouverts ?
{: faq}

Par défaut, le client de base dispose d'une technologie de pointe lui permettant de traiter la plupart des fichiers ouverts qui s'exécutent sur le système d'exploitation.

<hr>

## Où puis-je trouver des informations sur la tarification ?
{: faq}

Pour plus d'informations, voir [Stockage de sauvegarde](https://www.ibm.com/cloud/backup-and-restore){: external} et [Sauvegarde IBM Cloud : tarification](https://www.ibm.com/cloud/backup/pricing){: external}.

<hr>

## La capacité {{site.data.keyword.backup_notm}} peut-elle être augmentée/réduite sans compromettre les sauvegardes ?
{: faq}

Vous pouvez augmenter ou réduire la taille de votre coffre via la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}. La modification de la capacité n'a aucun impact sur l'intégrité des données qui sont stockées dans le coffre. Pour plus d'informations, voir [Extension de la capacité](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity).

<hr>

## Que se passe-t-il lorsque la capacité {{site.data.keyword.backup_notm}} est dépassée ?
{: faq}

Vous pouvez toujours enregistrer et récupérer vos sauvegardes même si vous avez atteint la limite de la capacité que vous avez achetée. Toutefois, vous devez vous attendre à des frais supplémentaires pour chaque Go additionnel utilisé au niveau de la facturation.

<hr>

## Comment configurer des notifications dans le portail {{site.data.keyword.backup_notm}} pour être alerté lorsqu'une sauvegarde échoue ?
{: faq}

Vous pouvez configurer des notifications dans l'onglet Avancé. Suivez les instructions qui figurent dans les **Liens rapides** du portail {{site.data.keyword.backup_notm}}.

<hr>

## Lorsque j'utilise le plug-in BMR, puis-je passer d'un disque unique à une grappe RAID ?

Oui, c'est tout à fait possible. Cependant, vous devez sélectionner une unité de grande capacité en raison de la réduction de taille provoquée par la grappe RAID.

<hr>

## Lorsque j'utilise le plug-in BMR, que se passe-t-il si l'image est restaurée sur un disque plus grand que le volume d'origine ?
{: faq}

Si vous restaurez l'image sur un disque de plus grande capacité que le volume d'origine, l'espace excédentaire est désaffecté. Si, par exemple, vous disposez d'une unité de 500 Go et que vous restaurez ses données sur un disque de 1 To, un espace disque de 500 Go est désaffecté. Avec Windows 2008, vous pouvez utiliser l'utilitaire disque intégré pour étendre la partition principale. Toutefois, il n'existe pas de fonction intégrée similaire dans Windows 2003, par conséquent, vous devez allouer l'espace d'une autre façon.

<hr>

## BMR peut-il être utilisé pour une sauvegarde régulière ?
{: faq}

La sauvegarde BMR n'est pas une image disque mais un système de sauvegarde d'image sur un volume système. Le système n'est pas destiné à être utilisé pour des sauvegardes régulières mais conjointement à celles-ci.  

<hr>

##BMR peut-il être utilisé pour des sauvegardes de base de données ?
{: faq}

Les sauvegardes de base de données doivent être réalisées séparément, avec les méthodes de sauvegarde {{site.data.keyword.backup_notm}} ordinaires. BMR ne vient pas remplacer les plug-ins SQL ou Oracle. Bien que BMR utilise la technologie VSS pour sauvegarder les fichiers ouverts, il n'est pas garanti que les fichiers sauvegardés soient toujours cohérents avec les transactions. Il est recommandé, pour ces types d'applications spécialisées, de créer deux travaux de sauvegarde : l'un pour sauvegarde du système d'exploitation et des fichiers binaires d'application, l'autre pour les données d'application.

<hr>

## Quel type de travaux de restauration puis-je effectuer avec BMR ?

Vous pouvez effectuer une restauration intégrale du système ou bien sélectionner dans la sauvegarde des fichiers individuels à restaurer. Le travail de sauvegarde BMR peut remplacer le travail de sauvegarde de vos fichiers actuels. La procédure de restauration est effectuée dans le système d'exploitation, tout comme un travail de sauvegarde traditionnel.

<hr>

## BMR dispose-t-il de fonctionnalités de sauvegarde de fichiers ouverts ?
{: faq}

BMR dispose de fonctionnalités de sauvegarde de fichiers ouverts. Toutefois, BMR ne vient pas remplacer les plug-ins SQL ou Oracle. Cliquez [ici](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin) pour les instructions d'installation du plug-in MSSQL.

<hr>

## Combien d'espace disque et de temps sont-ils nécessaires pour une restauration BMR ?
{: faq}

Une sauvegarde qui est réalisée à partir d'une installation par défaut utilise environ 6 Go. Une restauration de ce type dure environ 15 minutes sur un port 1 Go. Cette procédure est également affectée par la vitesse du port privé. Si vous avez besoin de sauvegardes et de restaurations plus rapides, vous devrez éventuellement utiliser un port plus véloce.

<hr>

## Rôle de VSS (Volume Shadow Copy Services) ?
{: faq}

La version actuelle du plug-in SQL Server utilise VSS (Volume Shadow Copy Services) pour réaliser des sauvegardes. Grâce à VSS, le plug-in SQL Server sauvegarde efficacement des bases de données SQL, même celles qui sont réparties sur plusieurs volumes. Les sauvegardes peuvent être effectuées tandis que les applications continuent d'écrire des données sur un volume. Le plug-in SQL Server permet une cohérence des données dans et entre les bases de données. VSS permet l'exécution simultanée de plusieurs sauvegardes.

<hr>

## La version 32 bits d'EVault for Windows 8 est-elle toujours prise en charge ?
{: faq}

Non. La version 32 bits de l'agent de logiciel de sauvegarde a été retirée avec les éditions Windows Server 2008 Standard et Datacenter en mars 2017.
