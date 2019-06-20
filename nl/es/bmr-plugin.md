---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Información sobre el plugin de restauración desde cero
{: #BMRplugin}

BMR es una solución de recuperación tras desastre. Puede utilizar BMR para restaurar el servidor desde cero después de que se produzca un desastre, como un error del sistema operativo o del hardware. Con BMR puede restaurar rápidamente la imagen del sistema desde una ubicación segura, gestionada por {{site.data.keyword.cloud}}.

BMR es un producto de Microsoft Windows solo para servidores físicos. No está disponible para servidores virtuales. No se da soporte a las restauraciones desde cero para distribuciones Linux. BMR sólo está soportado por el agente de copia de seguridad 8.30 o versiones anteriores. (30 de junio de 2018).
{:important}

## Funciones proporcionadas
{: #BMRcapabilities}

- Restaurar el sistema a un punto en el tiempo seleccionado.
- Restaurar el sistema a partir de copias de seguridad basadas en imagen o en archivo.
- Restaurar el sistema a partir de copias de seguridad guardadas en {{site.data.keyword.backup_notm}}.
- Una transacción de recuperación que se puede iniciar y que pueda utilizar para restaurar los datos sin un sistema de arranque.

## Instalación del plugin de BMR
{: #installingBMR}

El plugin se instala durante la instalación del agente Windows. El plugin se puede instalar al mismo tiempo que el agente o bien se puede instalar más adelante, volviendo a ejecutar la instalación con la selección **Modificar**.

## Configuración de un trabajo de copia de seguridad de BMR
{: #configBMRplugin}

For more information, see [Configuración de trabajos de copia de seguridad de BMR](/docs/infrastructure/Backup?topic=Backup-configureBMR).

## Restauración de una imagen de volumen del sistema BMR
{: #restoringBMimage}
Para obtener más información, consulte [Restauración de una imagen de volumen del sistema BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

## Descarga de la guía del usuario
{: #BMRUserGuide}

Conéctese a la red de {{site.data.keyword.cloud}} con {{site.data.keyword.BluVPN}} para poder acceder y descargar la guía del usuario desde la [Documentación descargable de {{site.data.keyword.backup_notm}}](http://downloads.service.softlayer.com/evault/Documentation/){: external}
