---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-26"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalación del plugin de restauración desde cero
{: #BMRplugin}

BMR es una solución de recuperación tras desastre. Puede utilizar BMR para restaurar el servidor desde cero después de que se produzca un desastre, como un error del sistema operativo o del hardware. Con BMR puede restaurar rápidamente la imagen del sistema desde una ubicación segura, gestionada por {{site.data.keyword.BluSoftlayer_full}}.

BMR es un producto de Microsoft Windows solo para servidores físicos. No está disponible para servidores virtuales. No se da soporte a las distribuciones de restauraciones desde cero de Linux. BMR sólo está soportado por el agente de copia de seguridad 8.30 o versiones anteriores. (30 de junio de 2018).
{:important}

**Funciones que se proporcionan**

- Restaurar el sistema a un punto en el tiempo seleccionado.
- Restaurar el sistema a partir de copias de seguridad basadas en imagen o en archivo.
- Restaurar el sistema a partir de copias de seguridad guardadas en {{site.data.keyword.backup_notm}}.
- Una transacción de recuperación que se puede iniciar y que pueda utilizar para restaurar los datos sin un sistema de arranque.

## Solicitud del plugin
{: #orderingBMR}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**. <br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione la cuenta y pulse **Solicitar plugins**.
4. Seleccione **Plugin de {{site.data.keyword.backup_notm}} - BMR (restauración desde cero)** y pulse **Continuar**.
5. Escriba su código de promoción, si lo tiene, y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque el recuadro para indicar que ha leído y que acepta los acuerdos de servicio de terceros.
8. Pulse **Realizar pedido**.

## Descarga de la guía del usuario
{: #BMRUserGuide}

Conéctese a la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder acceder y descargar la guía del usuario desde la [Documentación descargable de {{site.data.keyword.backup_notm}}![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
