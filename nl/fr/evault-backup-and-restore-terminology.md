---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Terminologie de sauvegarde et de restauration EVault 

## Technologie delta :
La toute première sauvegarde est une sauvegarde "de départ" (complète et intégrale), la suivante et les autres étant de type "delta" (à savoir, uniquement des modifications), mais qui sont équivalentes et considérées elles-aussi comme "sauvegarde complète". En d'autres termes, vous pouvez restaurer tous les fichiers, ou ceux de votre choix, depuis celle-ci. Cette technologie permet d'effectuer des "sauvegardes complètes" à chaque session, mais économise un espace considérable dans le coffre et réduit la durée d'exécution de chaque sauvegarde ultérieure.

## Schémas de conservation : 
EVault permet une conservation des données en fonction du délai jusqu'auquel vous désirez pouvoir remonter. Le schéma de conservation quotidienne conserve les données pendant 7 jours, tandis que le schéma hebdomadaire les conserve pendant 1 mois et le schéma mensuel, pendant 1 an. A la fin de chaque période, les données les plus anciennes sont expurgées et la première sauvegarde delta effectuée devient le point de restauration le plus éloigné disponible. 

## Compression : 
EVault propose 6 types de solutions de chiffrement pour vos données : DES 56 bits, Blowfish 56 bits, Triple DES 112 bits, Blowfish 128 bits, AES 128 bits et AES 256 bits. Les ratios de compression admettent une compression allant de 0 % jusqu'à une compression maximale pouvant aller, selon le type de fichier, de 20 à 30 %.

## Chiffrement :
Par défaut, tous les chiffrements en ligne (OTW) utilisent un chiffrement AES 128 bits. Si vous voulez que les données soient stockées sous un format chiffré, plusieurs options sont disponibles dans le cadre du processus de sauvegarde. Notez que si vous égarez votre mot de passe, vous ne pourrez PAS récupérer vos données. 

## Sauvegardes spéciales : 
Les sauvegardes de l'état du système incluent, sans s'y limiter, la base de données d'enregistrement de classe COM +, le registre, les fichiers d'amorçage, les fichiers système, et le compteur de performance (le tout dépendant de votre système). Les fichiers système varient selon le système d'exploitation et les service packs. On en compte généralement plusieurs milliers. MS Windows établit une liste dynamique de ces DLL lorsque vous les incluez dans la sauvegarde. L'inclusion des fichiers système vous permet une reprise en cas de fichiers système endommagés ou si vous désinstallez par inadvertance des service packs, ou si vous désirez effectuer une restauration bare-metal. Elle vous permet de revenir à l'état de la sauvegarde sans avoir à réinstaller le système d'exploitation depuis le kit d'installation, puis d'installer chaque service pack séparément. 

## Fichiers ouverts : 
Par défaut, le client de base dispose d'une technologie de pointe lui permettant de traiter la plupart des fichiers ouverts s'exécutant sur le système d'exploitation. Dans de rares cas, si la sauvegarde échoue en raison de limitations de fichiers ouverts, vous pouvez acquérir des plug-ins annexes pour un traitement amélioré de ces fichiers. En général, vous n'aurez pas besoin du plug-in de fichier ouvert à moins de rencontrer dans vos sauvegardes des erreurs concernant des fichiers ouverts, auquel cas vous pourrez commander les plug-ins.
