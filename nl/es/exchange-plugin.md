---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalación del plugin Exchange
{: #Exchangeplugin}

El plugin Exchange se instala con el agente Windows en el host. Mediante el portal de {{site.data.keyword.backup_notm}} puede configurar trabajos, hacer copia de seguridad de bases de datos Exchange en una caja fuerte remota segura y restaurar bases de datos Exchange. El plugin se integra en la arquitectura existente.

**Funciones que se proporcionan**

- Capacidad de hacer copia de seguridad y de restaurar bases de datos de Microsoft Exchange.

## Solicitud del plugin
{: #orderingExchangePlugin}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.<br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione la cuenta y pulse **Solicitar plugins**.
4. Seleccione **{{site.data.keyword.backup_notm}} Plugin - Exchange** y pulse **Continuar**.
5. Escriba su código de promoción, si lo tiene, y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque el recuadro para indicar que ha leído y que acepta los acuerdos de servicio de terceros.
8. Pulse **Realizar pedido**.

## Instalación del plugin
{: #installExchangePlugin}

El plugin Exchange se instala durante la instalación del agente Windows de 64 bits. El plugin se puede instalar al mismo tiempo que el agente o bien se puede instalar más adelante, volviendo a ejecutar la instalación con la selección **Modificar**.

Antes de instalar el plugin para el servidor Microsoft Windows, detenga ambos servicios de {{site.data.keyword.backup_notm}} en `services.msc`.
{:tip}

1. Vaya a la carpeta `c:\installs\{{site.data.keyword.backup_notm}}` y ejecute el archivo .exe con el número de revisión más alto.
2. En la pantalla de idioma, pulse **Aceptar**
3. En la pantalla de bienvenida, pulse **Siguiente**
4. Seleccione la opción **Modificar instalación** y pulse **Siguiente**.
5. Seleccione la opción **Dejar sin cambios** y pulse **Siguiente**.
6. En la pantalla de configuración personalizada, seleccione cada plugin que haya adquirido.
7. Seleccione **Esta característica se instalará en...** y luego pulse **Siguiente**.
8. Seleccione **Conservar mi registro actual** y pulse **Siguiente**.
9. Pulse **Instalar**.
10. Una vez instalados, compruebe que ambos servicios están habilitados y en ejecución.
11. Si el portal de {{site.data.keyword.backup_notm}} puede ver o acceder a la base de datos, significa que la instalación se ha realizado correctamente.

## Descarga de la guía del usuario
{: #ExchangeUserGuide}

Conéctese a la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder acceder y descargar la guía del usuario desde la [Documentación descargable de {{site.data.keyword.backup_notm}}![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. En la guía se describe cómo hacer copia de seguridad y restaurar bases de datos de Microsoft Exchange mediante el plugin Exchange. En la guía también se describe cómo compartir un conjunto seguro de copia de seguridad de DR. Con un conjunto seguro de copia de seguridad de DR, puede restaurar buzones, mensajes u otros objetos específicos en un archivo .pst utilizando la aplicación Granular Restore para Microsoft Exchange.
