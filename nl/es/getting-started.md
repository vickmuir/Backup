---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}_
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Guía de aprendizaje de iniciación
{: #getting-started}

Las copias de seguridad garantizan que los datos se almacenan de forma segura fuera de su dispositivo y están protegidos si se pierden. {{site.data.keyword.backup_full}} es un sistema de copia de seguridad automático basado en agente que se gestiona mediante el programa de utilidad de gestión basado en navegador del portal de {{site.data.keyword.backup_notm}}. {{site.data.keyword.backup_notm}} proporciona a los usuarios un método de hacer copia de seguridad de los datos entre servidores de uno o varios centros de datos de la red de {{site.data.keyword.BluSoftlayer_full}}. Los administradores pueden establecer que las copias de seguridad sigan una planificación diaria, semanal o personalizada que abarque sistemas completos, directorios específicos o incluso archivos individuales. Los plugins adicionales garantizan la compatibilidad con software como Microsoft Exchange y Microsoft SQL y otros tipos de software de terceros y permiten a los usuarios completar una restauración desde cero.
{:shortdesc}

## Antes de empezar
{: #prereqs}

Debe tener una licencia válida para utilizar IBM Cloud Backup. Puede adquirir el servicio {{site.data.keyword.backup_notm}} de dos maneras.

- [Adquisición de copias de seguridad cuando se solicita un servidor](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [Adquisición de copias de seguridad como actualización](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

Para obtener más información sobre cómo solicitarlo y los precios, consulte [Suministro de {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering).

## Instalación del agente de {{site.data.keyword.backup_notm}}

El agente de {{site.data.keyword.backup_notm}} está soportado en los sistemas operativos siguientes:

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Siga las instrucciones adecuadas para su sistema operativo,
- [Instalación del cliente de copia de seguridad en Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Instalación del cliente de copia de seguridad en Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Instalación del cliente de copia de seguridad en Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## Acceso al portal de {{site.data.keyword.backup_notm}} (anteriormente conocido como WebCC)

El portal de {{site.data.keyword.backup_notm}} se utiliza para interactuar con todos los servicios de {{site.data.keyword.backup_notm}} que ofrece {{site.data.keyword.BluSoftlayer_full}}. El portal de {{site.data.keyword.backup_notm}} es un cliente basado en navegador que se ejecuta en la red privada de {{site.data.keyword.BluSoftlayer_full}} y que permite el control completo de cualquier servicio de {{site.data.keyword.backup_notm}}, incluidas operaciones de configuración y de restauración.

1. Acceda a la red privada a través de VPN.

   No se puede acceder al portal de {{site.data.keyword.backup_notm}} a través de la red pública. En primer lugar se debe establecer una conexión VPN.
   {:important}
2. Acceda a la pantalla de almacenamiento de copia de seguridad en [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
3. Pulse en cualquier lugar de la fila del servicio de {{site.data.keyword.backup_notm}} que desea ver para expandir la vista.
4. Pulse el **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal en su navegador.

## Configuración del agente de copia de seguridad y de la planificación de copias de seguridad

Después de haber solicitado el {{site.data.keyword.backup_notm}} y de haber instalado el agente en el servidor, puede empezar a crear copias de seguridad de los datos. Siga estos pasos para configurar el agente y la planificación de la retención.

1. Inicie la sesión en el portal de {{site.data.keyword.backup_notm}}.
2. Pulse **Todos los agentes**> **Agentes no configurados**.
3. Pulse el enlace **Este es un nuevo agente que me gustaría configurar**. Siga los pasos del proceso y especifique la siguiente información:
   1. Configuración del agente: especifique la descripción del agente y pulse **Siguiente**.
   2. Selección de tipo de trabajo: especifique el nombre del trabajo, la descripción del trabajo y el tipo de origen de la copia de seguridad y pulse **Siguiente**.
   3. Selección: seleccione los directorios y pulse **Incluir...**
   4. Opciones: especifique contraseñas
   5. Planificación: pulse **Añadir** para crear una planificación y pulse **Siguiente**.
   6. Seleccione la caja fuerte predeterminada y pulse **Aceptar**.
   7. Pulse **Guardar**.
4. Cree una planificación de retención.
   1. Seleccione **Editar** > **Configuración del agente**.
   2. Pulse **Añadir**.
   3. Especifique los detalles de retención.
   4. Pulse **Aceptar**.
   5. Pulse **Guardar**.

      Para obtener más información sobre los esquemas de retención, consulte las [Preguntas frecuentes](/docs/infrastructure/Backup?topic=Backup-faqs#faqs).
      {:tip}

## Ejecución del primer trabajo de copia de seguridad

1. Inicie la sesión en el portal de {{site.data.keyword.backup_notm}}.
2. Pulse **Todos los agentes** y seleccione el agente que ha configurado.
3. Pulse **Ejecutar copia de seguridad**.
4. Confirme el destino y seleccione un esquema de retención.
5. Pulse **Iniciar copia de seguridad**. Puede ver los detalles de la copia de seguridad mientras se está ejecutando el proceso.
6. Cuando finalice la copia de seguridad, pulse **Cerrar**.

Para obtener más información, consulte la sección [Configuración de una copia de seguridad simple a nivel de archivo en Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Acceso y visualización de los detalles de almacenamiento de {{site.data.keyword.backup_notm}} en la consola

Puede ver los detalles de almacenamiento del servicio en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} y en el {{site.data.keyword.slportal}} siempre que lo desee. Los detalles que se pueden ver incluyen contraseña, dirección de almacenamiento y uso asociado con el servicio de {{site.data.keyword.backup_notm}} seleccionado.

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.</br>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** y seleccione **Copia de seguridad** en la lista.
2. Pulse en cualquier lugar de la fila correspondiente a la caja fuerte cuyos detalles de almacenamiento desea ver. En esta vista la contraseña no resulta visible.
3. Pulse el recuadro de selección **Mostrar** junto al campo **Contraseña** para ver la contraseña correspondiente al servicio de {{site.data.keyword.backup_notm}} seleccionado.

Los cambios realizados en la contraseña de la copia de seguridad de {{site.data.keyword.backup_notm}} en el {{site.data.keyword.slportal}} se realizan en el propio servicio. Para restablecer la contraseña, siga los pasos de la sección [Cambio de la contraseña del servicio de copia de seguridad](/docs/infrastructure/Backup?topic=Backup-changePassword).
{:important}

## Obtención de más ayuda en línea

Los sistemas del portal de {{site.data.keyword.backup_notm}} están plenamente documentados y se puede acceder a soporte para la aplicación dentro del propio portal de {{site.data.keyword.backup_notm}}. Pulse el signo de interrogación blanco dentro de un círculo azul que se encuentra en la parte superior derecha para obtener **Ayuda**. Pulse cualquier artículo o tema en la barra de navegación de la parte izquierda para ver más información.
